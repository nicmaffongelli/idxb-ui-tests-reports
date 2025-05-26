# Test info

- Name: Type of user: Client >> MW Menu: Design >> Sub-menu: Settings >> Sub-menu: Global >> Sub-menu: Results >> Client can perform a search in Address Search FE page and the number of results is 25 - User: Client-Elite-1-Existing
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/settings/resultsGlobalPreferences.spec.ts:33:29

# Error details

```
TimeoutError: locator.click: Timeout 20000ms exceeded.
Call log:
  - waiting for locator('#IDX-formSubmit')

    at FrontEndAddressSearchPage.performSearch (/opt/atlassian/pipelines/agent/build/tests/pages/client/frontEndPages/FrontEndAddressSearchPage.ts:108:29)
    at /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/settings/resultsGlobalPreferences.spec.ts:39:68
```

# Page snapshot

```yaml
- text: "{\"message\":\"failure to get a peer from the ring-balancer\"}"
```

# Test source

```ts
   8 |
   9 | export class FrontEndAddressSearchPage extends BasePage {
   10 |   // Search form elements
   11 |   private readonly addressInput: Locator;
   12 |   private readonly cczSelect: Locator; // City, County, Zip select
   13 |   private readonly propertyTypeSelect: Locator;
   14 |   private readonly searchRefinementSelect: Locator;
   15 |   private readonly searchButton: Locator;
   16 |
   17 |   // Results page elements
   18 |   private readonly listingCardImageOverlays: Locator; // Used to count results
   19 |   private readonly resultsPerPageSelect: Locator;
   20 |   private readonly totalResults: Locator; // For checking total result count text
   21 |
   22 |   // Address search page container
   23 |   private readonly addressSearchPageContainer: Locator;
   24 |   private readonly navigationButtonsBar: Locator;
   25 |   private readonly actionsButtons: Locator;
   26 |
   27 |   /**
   28 |    * Constructor initializes all page elements
   29 |    * @param page Playwright page object
   30 |    */
   31 |   constructor(page: Page) {
   32 |     super(page);
   33 |
   34 |     // Search form elements
   35 |     this.addressInput = page.locator('#IDX-address');
   36 |     this.cczSelect = page.locator('#IDX-ccz-select');
   37 |     this.propertyTypeSelect = page.locator('#IDX-pt');
   38 |     this.searchRefinementSelect = page.locator('#IDX-searchRefinement');
   39 |     this.searchButton = page.locator('#IDX-formSubmit');
   40 |
   41 |     // Results page elements
   42 |     this.listingCardImageOverlays = page.locator('.idx-listing-card__image-overlay');
   43 |     this.resultsPerPageSelect = page.locator('#IDX-resultsPerPage');
   44 |     this.totalResults = page.locator('.IDX-resultsCountMessage');
   45 |
   46 |     // Address search page container
   47 |     this.addressSearchPageContainer = page.locator('#IDX-searchPageWrapper');
   48 |     this.navigationButtonsBar = page.getByRole('navigation');
   49 |     this.actionsButtons = page.locator('#IDX-action-buttons');
   50 |   }
   51 |
   52 |   /**
   53 |    * Navigate to the Address Search page
   54 |    */
   55 |   async goto(userSubdomain: string): Promise<void> {
   56 |     await this.page.goto(`https://${userSubdomain}.${envConfig.URL_ENV_PART}.com/idx/search/address`);
   57 |   }
   58 |
   59 |   /**
   60 |    * Enter address search criteria
   61 |    * @param address The address to search for
   62 |    */
   63 |   async enterAddress(address: string): Promise<void> {
   64 |     await this.addressInput.fill(address);
   65 |   }
   66 |
   67 |   /**
   68 |    * Select a city, county, or postal code
   69 |    * @param value The value to select
   70 |    * @param type The type (city, county, zipcode)
   71 |    */
   72 |   async selectCCZ(value: string, type: 'city' | 'county' | 'zipcode'): Promise<void> {
   73 |     // Open the dropdown
   74 |     await this.cczSelect.click();
   75 |     
   76 |     // Find and click the option with matching value and type
   77 |     const option = this.page.locator(`#select2-IDX-ccz-select-results option[value="${value}"][data-type="${type}"]`);
   78 |     await option.click();
   79 |   }
   80 |
   81 |   /**
   82 |    * Select property type
   83 |    * @param propertyType The property type value to select
   84 |    */
   85 |   async selectPropertyType(propertyType: string): Promise<void> {
   86 |     await this.propertyTypeSelect.selectOption(propertyType);
   87 |   }
   88 |
   89 |   /**
   90 |    * Select search refinement options
   91 |    * @param refinements Array of refinement options to select
   92 |    */
   93 |   async selectRefinements(refinements: string[]): Promise<void> {
   94 |     await this.searchRefinementSelect.click();
   95 |     
   96 |     for (const refinement of refinements) {
   97 |       await this.page.locator(`#select2-IDX-searchRefinement-results option[value="${refinement}"]`).click();
   98 |     }
   99 |     
  100 |     // Click away to close dropdown
  101 |     await this.page.click('body', { position: { x: 0, y: 0 } });
  102 |   }
  103 |
  104 |   /**
  105 |    * Perform search with current criteria
  106 |    */
  107 |   async performSearch(): Promise<void> {
> 108 |     await this.searchButton.click();
      |                             ^ TimeoutError: locator.click: Timeout 20000ms exceeded.
  109 |     await waitForPageToBeFullyLoaded(this.page);
  110 |   }
  111 |
  112 |   /**
  113 |    * Count the number of listings on the results page
  114 |    * @returns The number of listings displayed
  115 |    */
  116 |   async countListings(): Promise<number> {
  117 |     await this.page.waitForSelector('.idx-listing-card__image-overlay');
  118 |     const count = await this.listingCardImageOverlays.count();
  119 |     return count;
  120 |   }
  121 |
  122 |   /**
  123 |    * Verify that the number of results matches the expected count
  124 |    * @param expectedCount The expected number of results
  125 |    */
  126 |   async verifyResultCount(expectedCount: number): Promise<void> {
  127 |     const actualCount = await this.countListings();
  128 |     expect(actualCount).toBe(expectedCount);
  129 |   }
  130 |
  131 |   /*
  132 |   * Get the address search page container
  133 |   * @returns The address search page container
  134 |   */
  135 |   async getAddressSearchPageContainer(): Promise<Locator> {
  136 |     return this.addressSearchPageContainer;
  137 |   }
  138 |
  139 |   /*
  140 |   * Get the navigation buttons bar
  141 |   * @returns The navigation buttons bar
  142 |   */
  143 |   async getNavigationButtonsBar(): Promise<Locator> {
  144 |     return this.navigationButtonsBar;
  145 |   }
  146 |
  147 |   /*
  148 |   * Get the actions buttons
  149 |   * @returns The actions buttons
  150 |   */
  151 |   async getActionsButtons(): Promise<Locator> {
  152 |     return this.actionsButtons;
  153 |   }
  154 |   
  155 | }
```