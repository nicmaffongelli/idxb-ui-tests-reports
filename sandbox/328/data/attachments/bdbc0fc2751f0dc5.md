# Test info

- Name: Type of user: Client >> MW Menu: Account >> Sub-menu: Users >> Sub-menu: Agents >> Create Agent - User: Client-Engage-1-Existing
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/clients/account/users/agents.spec.ts:26:25

# Error details

```
Error: Timed out 20000ms waiting for expect(locator).toBeVisible()

Locator: locator('tr:has(td:text-is("idxqamv+d90d85da-600e-4528-a7e0-a964aab9f983@gmail.com"))')
Expected: visible
Received: <element(s) not found>
Call log:
  - expect.toBeVisible with timeout 20000ms
  - waiting for locator('tr:has(td:text-is("idxqamv+d90d85da-600e-4528-a7e0-a964aab9f983@gmail.com"))')

    at ManageAgentsPage.verifyAgentExistsByEmail (/opt/atlassian/pipelines/agent/build/tests/pages/client/account/users/ManageAgentsPage.ts:97:32)
    at /opt/atlassian/pipelines/agent/build/tests/specs/clients/account/users/agents.spec.ts:37:25
```

# Page snapshot

```yaml
- navigation:
  - link "IDX Broker":
    - /url: /mgmt/dashboard
    - img "IDX Broker"
  - list:
    - listitem:
      - text: Sandbox
      - strong: "Signed in as:"
      - text: Nic (3265)
    - listitem:
      - text: "12"
      - img
- text: Notifications
- button "Clear All"
- text: retail clients only - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: all clients - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: retail clients only - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: all clients - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: retail clients only - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: all clients - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: retail clients only - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: all clients - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: retail clients only - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: all clients - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: retail clients only - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: all clients - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- navigation:
  - list:
    - listitem: Home +
    - listitem: Leads +
    - listitem: Listings +
    - listitem: Messages +
    - listitem:
      - link "MLS":
        - /url: /mgmt/mls-membership
    - listitem: Design +
    - listitem: Account -
    - listitem: Support +
- listitem:
  - link "Page Help":
    - /url: "#"
- heading "Agents manage your agents" [level=1]
- link "Add Agent":
  - /url: /mgmt/agents/create
- link "Import":
  - /url: /mgmt/agents/import
- link "Export":
  - /url: /mgmt/users/exports/create
- link "Set Global Permissions":
  - /url: "#globalPermissions"
- grid:
  - text: Show
  - combobox "Show entries":
    - option "10" [selected]
    - option "25"
    - option "50"
    - option "100"
  - text: "entries Search:"
  - 'textbox "Search: ? "': idxqamv+d90d85da-600e-4528-a7e0-a964aab9f983@gmail.com
  - link "?":
    - /url: "#"
  - link "":
    - /url: "#"
  - table:
    - rowgroup:
      - 'row "First Name: activate to sort column ascending Last Name: activate to sort column descending User ID: activate to sort column ascending Email: activate to sort column ascending Category: activate to sort column ascending Last Login: activate to sort column ascending Tools"':
        - columnheader:
          - checkbox
        - 'columnheader "First Name: activate to sort column ascending"': First Name
        - 'columnheader "Last Name: activate to sort column descending"': Last Name
        - 'columnheader "User ID: activate to sort column ascending"': User ID
        - 'columnheader "Email: activate to sort column ascending"': Email
        - 'columnheader "Category: activate to sort column ascending"': Category
        - 'columnheader "Last Login: activate to sort column ascending"': Last Login
        - columnheader "Tools"
    - alert:
      - row "No agents to display. You can add an agent or import an agent.":
        - cell "No agents to display. You can add an agent or import an agent.":
          - text: No agents to display. You can
          - link "add an agent":
            - /url: /mgmt/agents/create
          - text: or
          - link "import an agent":
            - /url: /mgmt/agents/import
          - text: .
  - text: Showing 0 to 0 of 0 entries
  - list:
    - listitem:
      - link "← Previous":
        - /url: "#"
    - listitem:
      - link "Next →":
        - /url: "#"
- paragraph:
  - text: "With selected:"
  - link "Delete Agents":
    - /url: "#bulkActionForm"
- paragraph:
  - text: Services © 2025
  - link "IDX Broker":
    - /url: https://www.idxbroker.com
  - text: . All rights reserved.
```

# Test source

```ts
   1 | import { Page, Locator, expect } from '@playwright/test';
   2 | import { BasePage } from '../../../BasePage';
   3 | import { EnvConfig } from '../../../../../env/env';
   4 | import { waitForPageToBeFullyLoaded } from '../../../../utils/page-utils';
   5 |
   6 | const envConfig = EnvConfig.get();
   7 |
   8 | /**
   9 |  * ManageAgentsPage class implements the Page Object Model pattern for the Manage Agents page
   10 |  * Provides methods and locators to interact with elements on the page
   11 |  */
   12 | export class ManageAgentsPage extends BasePage {
   13 |     // Table locators
   14 |     readonly agentsTable: Locator;
   15 |     readonly searchInput: Locator;
   16 |     readonly clearSearchButton: Locator;
   17 |     readonly pageLength: Locator;
   18 |     readonly totalEntriesInfo: Locator;
   19 |     
   20 |     // Action buttons
   21 |     readonly addAgentButton: Locator;
   22 |     readonly importAgentButton: Locator;
   23 |     readonly exportAgentButton: Locator;
   24 |     readonly globalPermissionsButton: Locator;
   25 |     readonly deleteSelectedAgentsButton: Locator;
   26 |     
   27 |     // Checkboxes
   28 |     readonly selectAllCheckbox: Locator;
   29 |
   30 |     // Confirmation dialog elements
   31 |     readonly confirmDialogYesButton: Locator;
   32 |     readonly confirmDialogNoButton: Locator;
   33 |     readonly confirmationDialog: Locator;
   34 |
   35 |     //Messages
   36 |     private readonly successMessage: Locator;
   37 |     
   38 |     /**
   39 |      * Constructor - initializes the page object and locators
   40 |      * @param page - Playwright page object
   41 |      */
   42 |     constructor(page: Page) {
   43 |         super(page);
   44 |         
   45 |         // Initialize locators
   46 |         this.agentsTable = page.locator('#agentListTable');
   47 |         this.searchInput = page.getByRole('textbox', { name: 'Search: ?' });
   48 |         this.clearSearchButton = page.locator('.idx-datatable-clear-before-add-on');
   49 |         this.pageLength = page.locator('[name="agentListTable_length"]');
   50 |         this.totalEntriesInfo = page.locator('#agentListTable_info');
   51 |         
   52 |         // Action buttons
   53 |         this.addAgentButton = page.getByRole('link', { name: 'Add Agent' });
   54 |         this.importAgentButton = page.getByRole('link', { name: 'Import' });
   55 |         this.exportAgentButton = page.getByRole('link', { name: 'Export Agent' });
   56 |         this.globalPermissionsButton = page.getByRole('link', { name: 'Set Global Permissions' });
   57 |         this.deleteSelectedAgentsButton = page.getByRole('link', { name: 'Delete Agents' });
   58 |         
   59 |         // Checkboxes
   60 |         this.selectAllCheckbox = page.locator('#checkAll');
   61 |
   62 |         // Confirmation dialog elements
   63 |         this.confirmDialogYesButton = page.getByRole('button', { name: 'Yes' });
   64 |         this.confirmDialogNoButton = page.getByRole('button', { name: 'No' });
   65 |         this.confirmationDialog = page.locator('#confirmationDialog');
   66 |
   67 |         this.successMessage = page.locator('#jGrowl');
   68 |     }
   69 |     
   70 |     /**
   71 |     * Go directly to the Add Agent page
   72 |     */
   73 |     async goto(){
   74 |         await this.page.goto(envConfig.MW_BASE_URL + '/mgmt/agents');
   75 |         await waitForPageToBeFullyLoaded(this.page);
   76 |     }
   77 |     
   78 |     /**
   79 |      * Search for an agent by a search term
   80 |      * @param searchTerm - The term to search for (email, name, etc.)
   81 |      */
   82 |     async searchForAgent(searchTerm: string) {
   83 |         await this.searchInput.fill(searchTerm);
   84 |         await this.page.keyboard.press('Enter');
   85 |         await waitForPageToBeFullyLoaded(this.page);
   86 |         // Wait for the search to complete
   87 |         await this.page.waitForTimeout(500); // Small delay to ensure the search is processed
   88 |     }
   89 |     
   90 |     /**
   91 |      * Verify agent exists by email
   92 |      * @param email - Email address to verify
   93 |      */
   94 |     async verifyAgentExistsByEmail(email: string) {
   95 |         await this.searchForAgent(email);
   96 |         const agentRow = this.page.locator(`tr:has(td:text-is("${email}"))`);
>  97 |         await expect(agentRow).toBeVisible();
      |                                ^ Error: Timed out 20000ms waiting for expect(locator).toBeVisible()
   98 |         await expect(agentRow).toContainText(email);
   99 |     }
  100 |     
  101 |
  102 |     /**
  103 |      * Edit an agent by email
  104 |      * @param email - Email address of the agent to edit
  105 |      */
  106 |     async editAgentByEmail(email: string) {
  107 |         await this.searchForAgent(email);
  108 |         const editButton = this.page.locator(`tr:has(td:text-is("${email}")) .idx-icon-edit`);
  109 |         await editButton.click();
  110 |         //TODO
  111 |         await this.page.waitForURL('**/mgmt/agents/**/edit');
  112 |     }
  113 |     
  114 |     /**
  115 |      * Login as an agent by email
  116 |      * @param email - Email address of the agent to login as
  117 |      */
  118 |     async loginAsAgentByEmail(email: string) {
  119 |         await this.searchForAgent(email);
  120 |         const loginButton = this.page.locator(`tr:has(td:text-is("${email}")) .idx-icon-login`);
  121 |         await loginButton.click();
  122 |     }
  123 |     
  124 |     /**
  125 |      * Select all agents using the "Select All" checkbox
  126 |      */
  127 |     async selectAllAgents() {
  128 |         await this.selectAllCheckbox.check();
  129 |         // Adding a small delay to ensure all checkboxes are updated
  130 |         await this.page.waitForTimeout(300);
  131 |     }
  132 |
  133 |     /**
  134 |      * Delete selected agents
  135 |      */
  136 |     async deleteSelectedAgents() {
  137 |         await this.deleteSelectedAgentsButton.click();
  138 |         // Assuming there's a confirmation dialog
  139 |         await this.confirmDialogYesButton.click();
  140 |         await waitForPageToBeFullyLoaded(this.page);
  141 |     }
  142 |     
  143 |     /**
  144 |      * Verify a specific success message is shown in the jGrowl notification
  145 |      * @param expectedMessage The expected message text to verify
  146 |      */
  147 |     async verifySuccessMessage(): Promise<void> {
  148 |         // Verify the text matches what we expect
  149 |         await expect(this.successMessage).toContainText('All Agents you selected have been deleted.');
  150 |     }
  151 |     
  152 | }
```