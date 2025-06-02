# Test info

- Name: Run these tests in serial mode >> Create custom city Location List and Verify City default selected list in Search Pages Preferences - Client: Client-Engage-2-Existing
- Location: /opt/atlassian/pipelines/agent/build/src/tests/specs/clients/06_design/04_settings/02_locations/createNewLocationList.spec.ts:36:13

# Error details

```
TimeoutError: locator.click: Timeout 20000ms exceeded.
Call log:
  - waiting for locator('#type-city')
    - locator resolved to <a id="type-city" class="btn span2" href="#bookmarkToStep2">City</a>
  - attempting click action
    2 × waiting for element to be visible, enabled and stable
      - element is not visible
    - retrying click action
    - waiting 20ms
    2 × waiting for element to be visible, enabled and stable
      - element is not visible
    - retrying click action
      - waiting 100ms
    38 × waiting for element to be visible, enabled and stable
       - element is not visible
     - retrying click action
       - waiting 500ms

    at CreateNewLocationListPage.selectCityListType (/opt/atlassian/pipelines/agent/build/src/page-objects/client/06_design/04_settings/02_locations/CreateNewLocationListPage.ts:63:31)
    at /opt/atlassian/pipelines/agent/build/src/tests/specs/clients/06_design/04_settings/02_locations/createNewLocationList.spec.ts:41:52
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
```

# Test source

```ts
   1 | import { Page, Locator, expect, BasePage, waitForPageToBeFullyLoaded } from '@shared-client-imports';
   2 |
   3 | export class CreateNewLocationListPage extends BasePage {
   4 |
   5 |   // Create List Locators
   6 |   readonly cityTypeButton: Locator;
   7 |   readonly addListItemInput: Locator;
   8 |   readonly citySuggestion: (cityName: string) => Locator; // Dynamic locator
   9 |   readonly addSingleItemButton: Locator;
   10 |   readonly addBulkStateSelect: Locator;
   11 |   readonly addBulkStateButton: Locator;
   12 |   readonly finalizeButton: Locator;
   13 |   readonly newListNameInput: Locator;
   14 |   readonly saveNewListButton: Locator;
   15 |
   16 |   // Apply to Search Pages Locators
   17 |   readonly applyToSearchPagesButton: Locator;
   18 |   readonly allSearchPagesCheckbox: Locator;
   19 |   readonly saveApplyChangesButton: Locator;
   20 |
   21 |   // Notification Locators (Added)
   22 |   readonly notificationContainer: Locator;
   23 |
   24 |   constructor(page: Page) {
   25 |     super(page);
   26 |
   27 |     // Create List Locators
   28 |     this.cityTypeButton = page.locator('#type-city'); // Using ID from HTML
   29 |     this.addListItemInput = page.locator('#addListItem');
   30 |
   31 |     // Function to get locator based on suggestion text
   32 |     this.citySuggestion = (suggestionText) => page.getByText(suggestionText);
   33 |     this.addSingleItemButton = page.locator('form:has(input[name="action"][value="addSingleItem"]) button[type="submit"]'); // Refined selector
   34 |     this.addBulkStateSelect = page.locator('#addBulkState');
   35 |     this.addBulkStateButton = page.locator('form:has(input[name="action"][value="addBulkState"]) button[type="submit"]'); // Refined selector
   36 |     this.finalizeButton = page.locator('#finalizeList'); // Using ID from HTML
   37 |     this.newListNameInput = page.locator('#newListName');
   38 |     this.saveNewListButton = page.locator('#saveNew'); // Using ID from HTML
   39 |
   40 |     // Apply to Search Pages Locators
   41 |     this.applyToSearchPagesButton = page.locator('#applyToSearchPage'); // Using ID from HTML
   42 |     this.allSearchPagesCheckbox = page.locator('#allSearchPages');
   43 |     this.saveApplyChangesButton = page.getByRole('button', { name: 'Save the Changes' });//page.locator('form:has(input[name="action"][value="applyListToSearchPages"]) button[type="submit"]'); // Refined selector
   44 |
   45 |     // Notification Locators (Added)
   46 |     this.notificationContainer = page.locator('#jGrowl'); // Added initialization
   47 |   }
   48 |
   49 |   // --- Actions ---
   50 |
   51 |   /**
   52 |    * Navigate directly to the Create Lists City/County/Postal Code list creation page
   53 |    */
   54 |   async goto(): Promise<void> {
   55 |     await this.page.goto(this.globalAndEnvironmentVariables.MW_BASE_URL + '/mgmt/location-lists/create');
   56 |     await waitForPageToBeFullyLoaded(this.page); // Added wait after goto
   57 |   }  
   58 |
   59 |   /**
   60 |    * Selects the 'City' list type.
   61 |    */
   62 |   async selectCityListType() {
>  63 |     await this.cityTypeButton.click();
      |                               ^ TimeoutError: locator.click: Timeout 20000ms exceeded.
   64 |   }
   65 |
   66 |   /**
   67 |    * Adds a single city to the list and verifies the success notification.
   68 |    * @param cityName - The city name to type into the input.
   69 |    * @param suggestionText - The exact text of the suggestion to click.
   70 |    */
   71 |   async addSingleCity(cityName: string, suggestionText: string) {
   72 |     await this.addListItemInput.click();
   73 |     // Use pressSequentially() instead of fill() to better simulate user typing and trigger autocomplete
   74 |     await this.addListItemInput.pressSequentially(cityName, { delay: 100 }); // Added small delay for robustness
   75 |     // Wait for suggestion explicitly if needed, otherwise Playwright might be fast enough
   76 |     await this.citySuggestion(suggestionText).click();
   77 |     await this.addSingleItemButton.click();
   78 |     await this.verifyItemAddedNotification(); // Added verification
   79 |   }
   80 |
   81 |   /**
   82 |    * Adds all cities from a specified state using the bulk add feature and verifies the success notification.
   83 |    * @param stateAbbreviation - The two-letter abbreviation for the state (e.g., 'OR').
   84 |    */
   85 |   async addBulkState(stateAbbreviation: string) {
   86 |     await this.addBulkStateSelect.selectOption(stateAbbreviation);
   87 |     await this.addBulkStateButton.click();
   88 |     await this.verifyBulkItemsAddedNotification(); // Added verification
   89 |   }
   90 |
   91 |   /**
   92 |    * Clicks the 'Finalize & Continue' button.
   93 |    */
   94 |   async finalizeListCreation() {
   95 |     await this.finalizeButton.click();
   96 |     await waitForPageToBeFullyLoaded(this.page);
   97 |   }
   98 |
   99 |   /**
  100 |    * Enters a name for the new list, saves it, and verifies the success notification.
  101 |    * @param listName - The name to give the new list.
  102 |    */
  103 |   async saveNewList(listName: string) {
  104 |     await this.newListNameInput.click();
  105 |     await this.newListNameInput.fill(listName); // fill is okay here as no autocomplete is expected
  106 |     await this.saveNewListButton.click();
  107 |     await this.verifyListSavedNotification(); // Added verification
  108 |     await waitForPageToBeFullyLoaded(this.page); // Wait after action/verification
  109 |   }
  110 |
  111 |   /**
  112 |    * Applies the newly created list to all search pages.
  113 |    * Note: Verification for the save action here might need a specific message.
  114 |    */
  115 |   async applyListToAllSearchPages() {
  116 |     await this.applyToSearchPagesButton.click();
  117 |     await this.allSearchPagesCheckbox.check();
  118 |     await this.saveApplyChangesButton.click();
  119 |     // TODO: Add verification for the apply changes success message if needed, e.g.:
  120 |     // await this.verifyApplyChangesSavedNotification('Expected success message here');
  121 |     await waitForPageToBeFullyLoaded(this.page);
  122 |   }
  123 |
  124 |   // --- Verification Methods (Added) ---
  125 |
  126 |   /**
  127 |    * Verifies the notification for successfully adding a single item.
  128 |    */
  129 |   async verifyItemAddedNotification() {
  130 |     await expect(this.notificationContainer).toContainText('Item added to your dynamic city list'); // Added timeout
  131 |   }
  132 |
  133 |   /**
  134 |    * Verifies the notification for successfully adding bulk items.
  135 |    * Uses partial text match as the exact number might vary.
  136 |    */
  137 |   async verifyBulkItemsAddedNotification() {
  138 |     await expect(this.notificationContainer).toContainText('list items added to your new custom list.'); // Added timeout
  139 |   }
  140 |
  141 |   /**
  142 |    * Verifies the notification for successfully saving the list.
  143 |    */
  144 |   async verifyListSavedNotification() {
  145 |     await expect(this.notificationContainer).toContainText('Custom list saved successfully'); // Added timeout
  146 |   }
  147 |
  148 | }
  149 |
```