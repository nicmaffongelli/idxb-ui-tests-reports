# Test info

- Name: Single Query search - Resource: Property - Class: Property - Limit 1 run first chunk
- Location: /opt/atlassian/pipelines/agent/build/src/tests/specs/superUser/04_mls/08_data/mlsDataExplorer.spec.ts:3:5

# Error details

```
TimeoutError: locator.selectOption: Timeout 20000ms exceeded.
Call log:
  - waiting for getByRole('combobox').nth(1)
    - locator resolved to <select class="span2" data-reactid=".0.3.1.0.0.0.1.0">…</select>
  - attempting select option action
    2 × waiting for element to be visible and enabled
      - did not find some options
    - retrying select option action
    - waiting 20ms
    2 × waiting for element to be visible and enabled
      - did not find some options
    - retrying select option action
      - waiting 100ms
    38 × waiting for element to be visible and enabled
       - did not find some options
     - retrying select option action
       - waiting 500ms

    at MlsDataExplorerPage.runPropertyQuery (/opt/atlassian/pipelines/agent/build/src/page-objects/superUser/04_mls/08_data/MlsDataExplorerPage.ts:52:33)
    at /opt/atlassian/pipelines/agent/build/src/tests/specs/superUser/04_mls/08_data/mlsDataExplorer.spec.ts:9:41
```

# Page snapshot

```yaml
- navigation:
  - link "IDX Broker":
    - /url: /mgmt/dashboard
    - img "IDX Broker"
  - list:
    - listitem:
      - text: Staging
      - strong: "Signed in as:"
      - text: IDXB
- text: Notifications
- strong: You’re all caught up! Keep an eye out for new notifications. We’ll post them here.
- navigation:
  - list:
    - listitem: Clients +
    - listitem: Partners +
    - listitem: Agent/Office +
    - listitem: MLS -
    - listitem: Listings +
    - listitem: Tools +
    - listitem: System +
- link "Similar Pages":
  - /url: "#"
- text: Change MLS
- textbox "Change MLS"
- heading "MLS Data Explorer b001 Regional Multiple Listing Service (RMLS) live" [level=1]
- button "Credentials"
- text: Target
- textbox "Target": https://resoapi.rmlsweb.com/reso/odata/
- text: Credentials
- combobox
- text: Username
- textbox "Username"
- text: Password
- textbox "Password": 9ade5f56db5a06d028cc59634f41e769
- link "Manage Credentials":
  - /url: /mgmt/mls/b001/manage-credentials
- navigation:
  - list:
    - link "Explore":
      - /url: "#/explore"
    - link "Property Types":
      - /url: "#/propertyTypes"
    - link "Single Query":
      - /url: "#/singleQuery"
    - link "Transaction":
      - /url: "#/transaction"
    - link "Get Objects":
      - /url: "#/getObjects"
    - link "Listing Lookup":
      - /url: "#/listingLookup"
    - link "Data Comparison":
      - /url: "#/dataComparison"
- text: Resource
- combobox:
  - option "---" [selected]
- text: Query String
- textbox
- button
- button "Share query"
- text: Class
- combobox:
  - option "---" [selected]
- text: Field Select
- textbox
- text: Limit
- textbox
- tablist:
  - tablist:
    - tab "Advanced Query Options" [selected]
    - tab "Save Options"
- tabpanel:
  - text: Date Field
  - textbox
  - text: Date Start
  - textbox
  - text: Post Request
  - checkbox
  - text: Use Offset Field
  - checkbox
- toolbar:
  - button "Run First Chunk" [disabled]
  - button "Run Full Query"
- tablist:
  - tablist:
    - tab "Mapped Field Search" [selected]
    - tab "Field Values Search"
- tabpanel "Mapped Field Search":
  - text: Mapped Field
  - textbox "Mapped Field"
- paragraph:
  - text: Services © 2025
  - link "IDX Broker":
    - /url: https://www.idxbroker.com
  - text: . All rights reserved.
```

# Test source

```ts
   1 | import { Page, Locator, BasePage, expect } from '@shared-client-imports';
   2 |
   3 | export class MlsDataExplorerPage extends BasePage {
   4 |   // Query elements
   5 |   private readonly singleQueryTab: Locator;
   6 |   private readonly entityTypeSelect: Locator;
   7 |   private readonly queryStringDropdown: Locator;
   8 |   private readonly propertyQueryOption: Locator;
   9 |   private readonly propertySelect: Locator;
  10 |   private readonly limitInput: Locator;
  11 |   private readonly runFirstChunkButton: Locator;
  12 |   
  13 |   // Results elements
  14 |   private readonly resultsContainer: Locator;
  15 |
  16 |   /**
  17 |    * Constructor initializes all page elements
  18 |    * @param page Playwright page object
  19 |    */
  20 |   constructor(page: Page) {
  21 |     super(page);
  22 |     
  23 |     // Query elements
  24 |     this.singleQueryTab = page.getByRole('link', { name: 'Single Query' });
  25 |     this.entityTypeSelect = page.getByRole('combobox').nth(1);
  26 |     this.queryStringDropdown = page.locator('#queryStringDropDown');
  27 |     this.propertyQueryOption = page.getByRole('menuitem', { 
  28 |       name: 'Property: (PropertyType eq Odata.Models.PropertyType\'Land\') and (MlsStatus eq Odata.Models.MlsStatus\'BumpableBuyer\' or MlsStatus eq Odata.Models.MlsStatus\'Active\' or MlsStatus eq Odata.Models.MlsStatus\'Pending\' or MlsStatus eq Odata.Models.MlsStatus\'ShortSalePending\')', 
  29 |       exact: true 
  30 |     });
  31 |     this.propertySelect = page.locator('div').filter({ hasText: /^---Property$/ }).getByRole('combobox');
  32 |     this.limitInput = page.locator('input[name="limit"]');
  33 |     this.runFirstChunkButton = page.getByRole('button', { name: 'Run First Chunk' });
  34 |     
  35 |     // Results elements
  36 |     this.resultsContainer = page.locator('#data-explorer');
  37 |   }
  38 |
  39 |   /**
  40 |    * Navigate directly to the MLS Data Explorer page for a specific MLS
  41 |    * @param mlsId The MLS ID to use (default: b001)
  42 |    */
  43 |   async goto(mlsId = 'b001'): Promise<void> {
  44 |     await this.page.goto(`${this.globalAndEnvironmentVariables.MW_BASE_URL}/mgmt/mls/${mlsId}/data-explorer#/singleQuery`);
  45 |   }
  46 |   
  47 |   /**
  48 |    * Run a property query
  49 |    * @param limit The number of results to limit to
  50 |    */
  51 |   async runPropertyQuery(limit: string): Promise<void> {
> 52 |     await this.entityTypeSelect.selectOption('Property');
     |                                 ^ TimeoutError: locator.selectOption: Timeout 20000ms exceeded.
  53 |     await this.queryStringDropdown.click();
  54 |     await this.propertyQueryOption.click();
  55 |     await this.propertySelect.selectOption('Property');
  56 |     await this.limitInput.click();
  57 |     await this.limitInput.fill(limit);
  58 |     await this.runFirstChunkButton.click();
  59 |   }
  60 |   
  61 |   /**
  62 |    * Verify query results
  63 |    */
  64 |   async verifyQueryResults(): Promise<void> {
  65 |     await expect(this.resultsContainer).toContainText('Single Query Performed Successfully.');
  66 |     await expect(this.resultsContainer).toContainText('We Got Data!');
  67 |   }
  68 |   
  69 |   /**
  70 |    * Run the complete workflow
  71 |    * @param mlsId The MLS ID to use
  72 |    * @param limit The number of results to limit to
  73 |    */
  74 |   async performCompleteWorkflow(mlsId: string, limit: string): Promise<void> {
  75 |     await this.goto(mlsId);
  76 |     await this.runPropertyQuery(limit);
  77 |     await this.verifyQueryResults();
  78 |   }
  79 | }
```