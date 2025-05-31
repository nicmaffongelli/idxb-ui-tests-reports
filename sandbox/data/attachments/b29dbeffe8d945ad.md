# Test info

- Name: MLS Global Settings Test - User: Client-Engage-2-Existing >> Should update MLS Custom Display name and verify it on front-end search page - User: Client-Engage-2-Existing
- Location: /opt/atlassian/pipelines/agent/build/src/tests/specs/clients/06_design/04_settings/03_mls/mlsGlobalSettings.spec.ts:11:13

# Error details

```
TimeoutError: locator.dblclick: Timeout 20000ms exceeded.
Call log:
  - waiting for locator('tr#mls-a411').locator('td.editable')
    - locator resolved to <td class=" editable">MLS Display 1748655763590</td>
  - attempting dblclick action
    2 × waiting for element to be visible, enabled and stable
      - element is not visible
    - retrying dblclick action
    - waiting 20ms
    2 × waiting for element to be visible, enabled and stable
      - element is not visible
    - retrying dblclick action
      - waiting 100ms
    38 × waiting for element to be visible, enabled and stable
       - element is not visible
     - retrying dblclick action
       - waiting 500ms

    at MlsSettingsPage.clickCustomDisplayEdit (/opt/atlassian/pipelines/agent/build/src/page-objects/client/06_design/04_settings/03_mls/MlsSettingsPage.ts:92:20)
    at MlsSettingsPage.editCustomDisplay (/opt/atlassian/pipelines/agent/build/src/page-objects/client/06_design/04_settings/03_mls/MlsSettingsPage.ts:129:20)
    at /opt/atlassian/pipelines/agent/build/src/tests/specs/clients/06_design/04_settings/03_mls/mlsGlobalSettings.spec.ts:25:42
```

# Page snapshot

```yaml
- navigation:
  - link "IDX Broker":
    - /url: /mgmt/dashboard
    - img "IDX Broker"
  - list:
    - listitem
- text: Notifications
- strong: You’re all caught up! Keep an eye out for new notifications. We’ll post them here.
- navigation:
  - list:
    - listitem
    - listitem
    - listitem
- paragraph:
  - text: Services © 2025
  - link "IDX Broker":
    - /url: https://www.idxbroker.com
  - text: . All rights reserved.
- status
- status
```

# Test source

```ts
   1 | import { Page, Locator, expect, BasePage, waitForPageToBeFullyLoaded } from '@shared-client-imports';
   2 |
   3 | /**
   4 |  * MlsSettingsPage
   5 |  * Page Object Model for the MLS Settings page in the middleware application
   6 |  */
   7 | export class MlsSettingsPage extends BasePage {
   8 |     // Table elements
   9 |     readonly mlsTable: Locator;
   10 |     readonly customDisplayInput: Locator;
   11 |     readonly propertyTypesTab: Locator;
   12 |     readonly propertyTypeTable: Locator;
   13 |     readonly propertyTypeCell: Locator;
   14 |     readonly rowCell: Locator;
   15 |     readonly tableHeader: Locator;
   16 |     readonly tableHeaderCells: Locator;
   17 |     readonly mlsRow: Locator;
   18 |
   19 |     /**
   20 |      * Constructor for MlsSettingsPage
   21 |      * @param page - Playwright page object
   22 |      */
   23 |     constructor(page: Page) {
   24 |         super(page);
   25 |         
   26 |         // Initialize locators
   27 |         this.mlsTable = page.locator('#mlsTable');
   28 |         // Input field appears after clicking edit
   29 |         this.customDisplayInput = page.locator('input[name="value"]');
   30 |         this.propertyTypesTab = page.getByRole('link', { name: 'Property Types' });
   31 |         this.propertyTypeTable = page.locator('#propTypeTable');
   32 |         this.propertyTypeCell = page.locator('td.propertyType');
   33 |         this.rowCell = page.getByRole('cell');
   34 |         this.tableHeader = this.mlsTable.locator('thead');
   35 |         this.tableHeaderCells = this.tableHeader.locator('th');
   36 |         this.mlsRow = page.locator('tr[id^="mls-"]');
   37 |     }
   38 |
   39 |     /**
   40 |      * Get the index of a column based on its header text.
   41 |      * @param headerText - The text of the header to find.
   42 |      * @returns Promise resolving to the 0-based index of the column.
   43 |      * @throws Error if the header is not found.
   44 |      */
   45 |     private async getColumnIndexByHeaderText(headerText: string): Promise<number> {
   46 |         const count = await this.tableHeaderCells.count();
   47 |         for (let i = 0; i < count; i++) {
   48 |             const text = await this.tableHeaderCells.nth(i).textContent();
   49 |             if (text?.trim() === headerText) {
   50 |                 return i;
   51 |             }
   52 |         }
   53 |         throw new Error(`Header with text "${headerText}" not found.`);
   54 |     }
   55 |
   56 |     /**
   57 |      * Get the locator for a specific row using its ID attribute.
   58 |      * @param mlsId - The MLS ID used in the row's ID (e.g., 'a411').
   59 |      * @returns Locator for the table row.
   60 |      */
   61 |     private getRowByMlsId(mlsId: string): Locator {
   62 |         // Use the specific ID of the row
   63 |         return this.page.locator(`tr#mls-${mlsId}`);
   64 |     }
   65 |
   66 |     /**
   67 |      * Get the locator for the Custom Display cell for a given MLS ID.
   68 |      * Uses the 'editable' class specific to this column within the row identified by ID.
   69 |      * @param mlsId - The MLS ID of the target row.
   70 |      * @returns Locator for the Custom Display cell.
   71 |      */
   72 |     private getCustomDisplayCell(mlsId: string): Locator {
   73 |         const row = this.getRowByMlsId(mlsId);
   74 |         // Target the cell within the ID'd row that has the 'editable' class
   75 |         return row.locator('td.editable');
   76 |     }
   77 |
   78 |     /**
   79 |      * Navigate to the MLS Settings page.
   80 |      */
   81 |     async goto(): Promise<void> {
   82 |         await this.page.goto(`${this.globalAndEnvironmentVariables.MW_BASE_URL}/mgmt/mls-settings`);
   83 |         await waitForPageToBeFullyLoaded(this.page);
   84 |     }
   85 |
   86 |     /**
   87 |      * Double-clicks the Custom Display cell to make it editable.
   88 |      * @param mlsId - The MLS ID of the target row (e.g., 'a411').
   89 |      */
   90 |     async clickCustomDisplayEdit(mlsId: string): Promise<void> {
   91 |         const cell = this.getCustomDisplayCell(mlsId);
>  92 |         await cell.dblclick();
      |                    ^ TimeoutError: locator.dblclick: Timeout 20000ms exceeded.
   93 |     }
   94 |
   95 |     /**
   96 |      * Set a new value for the Custom Display field for a specific MLS row.
   97 |      * Assumes the edit mode is active (cell was double-clicked).
   98 |      * @param mlsId - The MLS ID of the target row.
   99 |      * @param value - The new value to set.
  100 |      */
  101 |     async setCustomDisplayValue(mlsId: string, value: string): Promise<void> {
  102 |         // Wait for the input field to appear after double-click
  103 |         await this.customDisplayInput.waitFor({ state: 'visible', timeout: 5000 });
  104 |         await this.customDisplayInput.fill(value);
  105 |         await this.customDisplayInput.press('Enter');
  106 |         // Wait for the value to be saved by checking the specific cell
  107 |         const cell = this.getCustomDisplayCell(mlsId);
  108 |         // Add a small wait for the text update to propagate after Enter press
  109 |         await this.page.waitForTimeout(500);
  110 |         await expect(cell).toContainText(value, { timeout: 10000 });
  111 |     }
  112 |
  113 |     /**
  114 |      * Get the current Custom Display value for a specific MLS row.
  115 |      * @param mlsId - The MLS ID of the target row.
  116 |      * @returns Promise resolving to the current custom display value.
  117 |      */
  118 |     async getCustomDisplayValue(mlsId: string): Promise<string> {
  119 |         const cell = this.getCustomDisplayCell(mlsId);
  120 |         return await cell.textContent() || '';
  121 |     }
  122 |
  123 |     /**
  124 |      * Edit the Custom Display value for a specific MLS row.
  125 |      * @param mlsId - The MLS ID of the target row (e.g., 'a411').
  126 |      * @param newValue - The new value to set for Custom Display.
  127 |      */
  128 |     async editCustomDisplay(mlsId: string, newValue: string): Promise<void> {
  129 |         await this.clickCustomDisplayEdit(mlsId);
  130 |         // Pass mlsId to setCustomDisplayValue
  131 |         await this.setCustomDisplayValue(mlsId, newValue);
  132 |     }
  133 |
  134 |     async dragRowToTargetRow(sourceRowDomId: string, targetRowDomId: string): Promise<void> {
  135 |         const sourceCell = this.rowCell.filter({ hasText: sourceRowDomId }).nth(1);
  136 |         const targetCell = this.rowCell.filter({ hasText: targetRowDomId }).nth(1);
  137 |         
  138 |         await sourceCell.dragTo(targetCell);
  139 |         
  140 |         await this.page.waitForTimeout(1000);
  141 |     }
  142 |
  143 |     /**
  144 |      * Clicks on the "Property Types" tab.
  145 |      * 
  146 |      */
  147 |     async goToPropertyTypesTab(): Promise<void> {
  148 |         // Using the role-based locator (or another Playwright-specific one)
  149 |         await this.propertyTypesTab.click();
  150 |         await waitForPageToBeFullyLoaded(this.page);
  151 |     }
  152 |
  153 |     // Inside PropertyTypesPage class
  154 |     async getPropertyTypeByRow(rowNumber: number): Promise<string> {
  155 |         const textContent = await this.propertyTypeTable
  156 |             .locator(`tbody tr:nth-child(${rowNumber})`)
  157 |             .locator(this.propertyTypeCell)
  158 |             .textContent();
  159 |         return (textContent || '').trim();
  160 |     }
  161 | }
  162 |
```