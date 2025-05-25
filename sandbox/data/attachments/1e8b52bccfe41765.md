# Test info

- Name: Type of user: Client >> MW Menu: Design >> Sub-menu: Settings >> Sub-menu: Global >> Sub-menu: Results >> Client can perform a search in Advanced Search FE page and the number of results is 25 - User: Client-Engage-1-Existing
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/settings/resultsGlobalPreferences.spec.ts:43:29

# Error details

```
TimeoutError: locator.click: Timeout 20000ms exceeded.
Call log:
  - waiting for locator('#IDX-formSubmit')

    at FrontEndAdvancedSearchPage.performSearch (/opt/atlassian/pipelines/agent/build/tests/pages/client/frontEndPages/FrontEndAdvancedSearchPage.ts:156:33)
    at /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/settings/resultsGlobalPreferences.spec.ts:49:69
```

# Page snapshot

```yaml
- text: "{\"message\":\"failure to get a peer from the ring-balancer\"}"
```

# Test source

```ts
   56 |      * @param page - Playwright page object
   57 |      */
   58 |     constructor(page: Page) {
   59 |         super(page);
   60 |         
   61 |         // Navigation elements
   62 |         this.searchNavItems = page.locator('.IDX-searchNavItem');
   63 |         this.advancedSearchNavLink = page.getByRole('link', { name: 'Advanced Search' });
   64 |         this.listingIdNavLink = page.getByRole('link', { name: 'Listing ID' });
   65 |         this.addressNavLink = page.getByRole('link', { name: 'Address' });
   66 |         this.aiSmartSearchNavLink = page.getByRole('link', { name: 'AI Smart Search' });
   67 |         this.mapSearchNavLink = page.getByRole('link', { name: 'Map Search' });
   68 |         
   69 |         // Search form elements
   70 |         this.searchForm = page.locator('#IDX-searchForm');
   71 |
   72 |         // Results page elements
   73 |         this.listingCardImageOverlays = page.locator('.idx-listing-card__image-overlay');
   74 |         this.firstListingCard = page.locator('.idx-listing-card__image-overlay').nth(24);
   75 |         this.disclaimer = page.locator('div[style*="text-align:left"][style*="visibility:visible"]');
   76 |
   77 |         // Location selection elements
   78 |         this.cczSelectDropdown = page.locator('#IDX-ccz-select');
   79 |         this.cczGroup = page.locator('#IDX-ccz-group');
   80 |         this.cczSearchBox = this.cczGroup.getByRole('searchbox');
   81 |         this.cczInputField = page.locator('.select2-container--open').getByRole('searchbox');
   82 |         
   83 |         // Price elements
   84 |         this.clearMinPriceField = page.locator('#select2-IDX-hp-container').getByTitle('Remove all items');
   85 |         this.clearMaxPriceField = page.locator('#select2-IDX-lp-container').getByTitle('Remove all items');
   86 |         
   87 |         // Property Type elements
   88 |         this.propertyTypeDropdown = page.locator('#select2-IDX-pt-container');
   89 |         
   90 |         // Beds and Baths elements
   91 |         this.bedroomsDropdown = page.locator('#IDX-bd');
   92 |         this.bathroomsDropdown = page.locator('#IDX-tb');
   93 |         
   94 |         // Additional filters
   95 |         this.sqftDropdown = page.locator('#IDX-sqft');
   96 |         this.acresDropdown = page.locator('#IDX-acres');
   97 |         this.priceReductionDropdown = page.locator('#IDX-reduced');
   98 |         this.statusDropdown = page.locator('#IDX-propStatus');
   99 |         this.searchRefinementDropdown = page.locator('#IDX-searchRefinement');
  100 |         this.resultsPerPageDropdown = page.locator('#IDX-per');
  101 |         this.sortByDropdown = page.locator('#IDX-srt');
  102 |         
  103 |         // Action buttons
  104 |         this.searchButton = page.locator('#IDX-formSubmit');
  105 |     }
  106 |     
  107 |     /**
  108 |      * Navigate to the advanced search page
  109 |     */ 
  110 |     async goto(clientDomain: string): Promise<void> {
  111 |         const domainPart = this.envConfig.URL_ENV_PART ? `.${this.envConfig.URL_ENV_PART}` : '';
  112 |         await this.page.goto(`https://${clientDomain}${domainPart}.com/idx/search/advanced`);
  113 |         await waitForPageToBeFullyLoaded(this.page);
  114 |     }
  115 |   
  116 |     // Snippet for FrontEndAdvancedSearchPage.ts
  117 |
  118 |     /**
  119 |      * Select an MLS by its display name in the MLS dropdown
  120 |      * @param displayName - The display name of the MLS to select
  121 |      */
  122 |     async selectMlsByDisplayName(displayName: string): Promise<void> {
  123 |         // Locator for the main display area (textbox) using its initial text
  124 |         // IMPORTANT: Assumes 'Regional Multiple Listing Service' is the predictable initial text.
  125 |         // Adjust if the default text can vary.
  126 |         const dropdownTrigger = this.page.getByTitle(displayName);
  127 |
  128 |         // 1. Click the dropdown display area to open the options
  129 |         await dropdownTrigger.click({ timeout: 10000 });
  130 |
  131 |         // 3. Locate and click the specific option by name within the results list
  132 |         const optionToSelect = this.page.locator('ul.select2-results__options').getByText(displayName, { exact: true });
  133 |         
  134 |         await optionToSelect.click({ timeout: 10000 });
  135 |     }
  136 |
  137 |     async clickPropertyTypeDropdown(): Promise<void> {
  138 |         await this.propertyTypeDropdown.click();
  139 |     }
  140 |
  141 |     async getSelectOptionByRow(rowNumber: number): Promise<string> {
  142 |         
  143 |         const labelText = await this.page.locator(`.select2-results__options li:nth-child(${rowNumber}) .IDX-custom-form-element__label`).textContent();
  144 |         return labelText || '';
  145 |     }
  146 |
  147 |     async clearMinPrice(): Promise<void> {
  148 |         await this.clearMinPriceField.click();
  149 |     }
  150 |
  151 |     async clearMaxPrice(): Promise<void> {
  152 |         await this.clearMaxPriceField.click();
  153 |     }
  154 |
  155 |     async performSearch(): Promise<void> {
> 156 |         await this.searchButton.click();
      |                                 ^ TimeoutError: locator.click: Timeout 20000ms exceeded.
  157 |         await waitForPageToBeFullyLoaded(this.page);
  158 |     }
  159 | /*
  160 |     async verifyResultCount(expectedCount: number): Promise<void> {
  161 |         const resultCount = await this.page.locator('.IDX-searchResultsCount').textContent();
  162 |         expect(resultCount).toContain(expectedCount.toString());
  163 |     }
  164 | */
  165 |     async verifyResultCount(expectedCount: number): Promise<void> {
  166 |         const resultCount = await this.listingCardImageOverlays.count();
  167 |         expect(resultCount).toEqual(expectedCount);
  168 |     }
  169 |
  170 |     async verifyDisclaimerContainsText(expectedText: string): Promise<void> {
  171 |         const disclaimer = await this.disclaimer.textContent();
  172 |         expect(disclaimer).toContain(expectedText);
  173 |     }
  174 |
  175 |     async clickFirstListingCard(): Promise<void> {
  176 |         await this.firstListingCard.click();
  177 |         await waitForPageToBeFullyLoaded(this.page);
  178 |     }
  179 | }
```