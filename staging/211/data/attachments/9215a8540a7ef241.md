# Test info

- Name: Type of user: Super User >> MW Menu: MLS >> Sub-menu: Data >> Sub-menu: MLS Data Explorer >> Single Query search - Resource: Property - Class: Property - Limit 1 run first chunk
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/superUser/mls/data/mlsDataExplorer.spec.ts:9:21

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
    36 × waiting for element to be visible and enabled
       - did not find some options
     - retrying select option action
       - waiting 500ms

    at MlsDataExplorerPage.runPropertyQuery (/opt/atlassian/pipelines/agent/build/tests/pages/superUser/mls/data/MlsDataExplorerPage.ts:53:33)
    at /opt/atlassian/pipelines/agent/build/tests/specs/superUser/mls/data/mlsDataExplorer.spec.ts:15:57
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
   1 | import { Page, Locator, expect } from '@playwright/test';
   2 | import { BasePage } from '../../../BasePage';
   3 |
   4 | export class MlsDataExplorerPage extends BasePage {
   5 |   // Query elements
   6 |   private readonly singleQueryTab: Locator;
   7 |   private readonly entityTypeSelect: Locator;
   8 |   private readonly queryStringDropdown: Locator;
   9 |   private readonly propertyQueryOption: Locator;
  10 |   private readonly propertySelect: Locator;
  11 |   private readonly limitInput: Locator;
  12 |   private readonly runFirstChunkButton: Locator;
  13 |   
  14 |   // Results elements
  15 |   private readonly resultsContainer: Locator;
  16 |
  17 |   /**
  18 |    * Constructor initializes all page elements
  19 |    * @param page Playwright page object
  20 |    */
  21 |   constructor(page: Page) {
  22 |     super(page);
  23 |     
  24 |     // Query elements
  25 |     this.singleQueryTab = page.getByRole('link', { name: 'Single Query' });
  26 |     this.entityTypeSelect = page.getByRole('combobox').nth(1);
  27 |     this.queryStringDropdown = page.locator('#queryStringDropDown');
  28 |     this.propertyQueryOption = page.getByRole('menuitem', { 
  29 |       name: 'Property: (PropertyType eq Odata.Models.PropertyType\'Land\') and (MlsStatus eq Odata.Models.MlsStatus\'BumpableBuyer\' or MlsStatus eq Odata.Models.MlsStatus\'Active\' or MlsStatus eq Odata.Models.MlsStatus\'Pending\' or MlsStatus eq Odata.Models.MlsStatus\'ShortSalePending\')', 
  30 |       exact: true 
  31 |     });
  32 |     this.propertySelect = page.locator('div').filter({ hasText: /^---Property$/ }).getByRole('combobox');
  33 |     this.limitInput = page.locator('input[name="limit"]');
  34 |     this.runFirstChunkButton = page.getByRole('button', { name: 'Run First Chunk' });
  35 |     
  36 |     // Results elements
  37 |     this.resultsContainer = page.locator('#data-explorer');
  38 |   }
  39 |
  40 |   /**
  41 |    * Navigate directly to the MLS Data Explorer page for a specific MLS
  42 |    * @param mlsId The MLS ID to use (default: b001)
  43 |    */
  44 |   async goto(mlsId = 'b001'): Promise<void> {
  45 |     await this.page.goto(`${this.envConfig.MW_BASE_URL}/mgmt/mls/${mlsId}/data-explorer#/singleQuery`);
  46 |   }
  47 |   
  48 |   /**
  49 |    * Run a property query
  50 |    * @param limit The number of results to limit to
  51 |    */
  52 |   async runPropertyQuery(limit: string): Promise<void> {
> 53 |     await this.entityTypeSelect.selectOption('Property');
     |                                 ^ TimeoutError: locator.selectOption: Timeout 20000ms exceeded.
  54 |     await this.queryStringDropdown.click();
  55 |     await this.propertyQueryOption.click();
  56 |     await this.propertySelect.selectOption('Property');
  57 |     await this.limitInput.click();
  58 |     await this.limitInput.fill(limit);
  59 |     await this.runFirstChunkButton.click();
  60 |   }
  61 |   
  62 |   /**
  63 |    * Verify query results
  64 |    */
  65 |   async verifyQueryResults(): Promise<void> {
  66 |     await expect(this.resultsContainer).toContainText('Single Query Performed Successfully.');
  67 |     await expect(this.resultsContainer).toContainText('We Got Data!');
  68 |   }
  69 |   
  70 |   /**
  71 |    * Run the complete workflow
  72 |    * @param mlsId The MLS ID to use
  73 |    * @param limit The number of results to limit to
  74 |    */
  75 |   async performCompleteWorkflow(mlsId: string, limit: string): Promise<void> {
  76 |     await this.goto(mlsId);
  77 |     await this.runPropertyQuery(limit);
  78 |     await this.verifyQueryResults();
  79 |   }
  80 | }
```