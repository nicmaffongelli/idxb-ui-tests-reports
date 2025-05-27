# Test info

- Name: User: Client-Core-1-Existing >> Client can perform a search in Basic Search FE page and the number of results is 25 - User: Client-Core-1-Existing
- Location: /opt/atlassian/pipelines/agent/build/src/tests/specs/clients/06_design/04_settings/01_global/resultsGlobalPreferences.spec.ts:34:13

# Error details

```
TimeoutError: page.goto: Timeout 20000ms exceeded.
Call log:
  - navigating to "https://1747064226435.idxstaging.com/idx/search/basic", waiting until "load"

    at FrontEndBasicSearchPage.goto (/opt/atlassian/pipelines/agent/build/src/page-objects/client/frontEndPages/FrontEndBasicSearchPage.ts:87:25)
    at /opt/atlassian/pipelines/agent/build/src/tests/specs/clients/06_design/04_settings/01_global/resultsGlobalPreferences.spec.ts:35:50
```

# Test source

```ts
   1 | import { Page, Locator, expect, BasePage, waitForPageToBeFullyLoaded } from '@shared-client-imports';
   2 |
   3 | /**
   4 |  * FrontEndBasicSearchPage
   5 |  * Page Object Model for the Front End Basic Search functionality
   6 |  */
   7 | export class FrontEndBasicSearchPage extends BasePage {
   8 |     // Navigation elements
   9 |     readonly advancedSearchNavLink: Locator;
   10 |     
   11 |     // Results page elements
   12 |     readonly listingCardImageOverlays: Locator;
   13 |     
   14 |     // Location selection elements
   15 |     readonly cczSelectDropdown: Locator;
   16 |     readonly cczGroup: Locator;
   17 |     readonly cczSearchBox: Locator;
   18 |     readonly cczInputField: Locator;
   19 |     readonly cczResultsContainer: Locator;
   20 |     readonly cczSuggestionOption: Locator;
   21 |     readonly cczSuggestionLabel: Locator;
   22 |     
   23 |     // Price elements
   24 |     readonly minPriceDropdown: Locator;
   25 |     readonly maxPriceDropdown: Locator;
   26 |     readonly selectedMinPrice: Locator;
   27 |     readonly selectedMaxPrice: Locator;
   28 |     
   29 |     // Property Type elements
   30 |     readonly propertyTypeDropdown: Locator;
   31 |     
   32 |     // Action buttons
   33 |     readonly searchButton: Locator;
   34 |
   35 |     // MLS selection elements
   36 |     readonly mlsDisplayNameContainer: Locator;
   37 |     
   38 |     // Select2 elements
   39 |     readonly select2ResultsOption: Locator;
   40 |     
   41 |     /**
   42 |      * Constructor for FrontEndBasicSearchPage
   43 |      * @param page - Playwright page object
   44 |      */
   45 |     constructor(page: Page) {
   46 |         super(page);
   47 |         
   48 |         // Navigation elements
   49 |         this.advancedSearchNavLink = page.getByRole('link', { name: 'Advanced Search' });
   50 |         
   51 |         // Results page elements
   52 |         this.listingCardImageOverlays = page.locator('.idx-listing-card__image-overlay');
   53 |         
   54 |         // Location selection elements
   55 |         this.cczSelectDropdown = page.locator('#IDX-ccz-select');
   56 |         this.cczGroup = page.locator('#IDX-ccz-group');
   57 |         this.cczSearchBox = this.cczGroup.getByRole('searchbox');
   58 |         this.cczInputField = page.locator('.select2-container--open').getByRole('searchbox');
   59 |         this.cczResultsContainer = page.locator('#select2-IDX-ccz-select-results');
   60 |         this.cczSuggestionOption = page.locator('#select2-IDX-ccz-select-results li[role="option"].select2-results__option');
   61 |         this.cczSuggestionLabel = page.locator('div.IDX-custom-form-element__label');
   62 |         
   63 |         // Price elements
   64 |         this.minPriceDropdown = page.locator('#IDX-lp');
   65 |         this.maxPriceDropdown = page.locator('#IDX-hp');
   66 |         this.selectedMinPrice = page.locator('#IDX-minPrice-group .select2-selection__rendered');
   67 |         this.selectedMaxPrice = page.locator('#IDX-maxPrice-group .select2-selection__rendered');
   68 |         
   69 |         // Property Type elements
   70 |         this.propertyTypeDropdown = page.locator('#IDX-pt');
   71 |         
   72 |         // Action buttons
   73 |         this.searchButton = page.locator('#IDX-formSubmit');
   74 |
   75 |         // MLS selection elements
   76 |         this.mlsDisplayNameContainer = page.locator('#select2-IDX-idxID-container');
   77 |
   78 |         // Select2 elements
   79 |         this.select2ResultsOption = page.locator('.select2-results__option');
   80 |     }
   81 |     
   82 |     /**
   83 |      * Navigate to the basic search page
   84 |     */ 
   85 |     async goto(clientDomain: string): Promise<void> {
   86 |         const domainPart = this.globalAndEnvironmentVariables.URL_ENV_PART ? `.${this.globalAndEnvironmentVariables.URL_ENV_PART}` : '';
>  87 |         await this.page.goto(`https://${clientDomain}${domainPart}.com/idx/search/basic`);
      |                         ^ TimeoutError: page.goto: Timeout 20000ms exceeded.
   88 |         await waitForPageToBeFullyLoaded(this.page);
   89 |     }
   90 |     
   91 |     /**
   92 |      * Get the currently selected minimum price
   93 |      * @returns Promise resolving to the selected min price text or value
   94 |      */
   95 |     async getSelectedMinPrice(): Promise<string> {
   96 |         try {
   97 |             // First try to get the visible text in the Select2 dropdown
   98 |             return await this.selectedMinPrice.textContent() || '';
   99 |         } catch {
  100 |             // Fallback to getting the actual value from the select element
  101 |             return await this.minPriceDropdown.inputValue();
  102 |         }
  103 |     }
  104 |     
  105 |     /**
  106 |      * Get the currently selected maximum price
  107 |      * @returns Promise resolving to the selected max price text or value
  108 |      */
  109 |     async getSelectedMaxPrice(): Promise<string> {
  110 |         try {
  111 |             // First try to get the visible text in the Select2 dropdown
  112 |             return await this.selectedMaxPrice.textContent() || '';
  113 |         } catch {
  114 |             // Fallback to getting the actual value from the select element
  115 |             return await this.maxPriceDropdown.inputValue();
  116 |         }
  117 |     }
  118 |     
  119 |     /**
  120 |      * Get the numeric value of minimum price (removes currency symbols and formatting)
  121 |      * @returns Promise resolving to the numeric value of min price
  122 |      */
  123 |     async getMinPriceValue(): Promise<number> {
  124 |         const priceText = await this.getSelectedMinPrice();
  125 |         // Extract numeric value from price text (removes $, commas, etc)
  126 |         const numericValue = priceText.replace(/[^0-9]/g, '');
  127 |         return numericValue ? parseInt(numericValue, 10) : 0;
  128 |     }
  129 |     
  130 |     /**
  131 |      * Get the numeric value of maximum price (removes currency symbols and formatting)
  132 |      * @returns Promise resolving to the numeric value of max price
  133 |      */
  134 |     async getMaxPriceValue(): Promise<number> {
  135 |         const priceText = await this.getSelectedMaxPrice();
  136 |         // Extract numeric value from price text (removes $, commas, etc)
  137 |         const numericValue = priceText.replace(/[^0-9]/g, '');
  138 |         return numericValue ? parseInt(numericValue, 10) : 0;
  139 |     }
  140 |     
  141 |     /**
  142 |      * Verify the minimum price is set to the expected value
  143 |      * @param expectedPrice Expected price value (number or formatted string)
  144 |      */
  145 |     async verifyMinPrice(expectedPrice: string | number): Promise<void> {
  146 |         let expectedNumeric: number;
  147 |         
  148 |         if (typeof expectedPrice === 'string') {
  149 |             // If expected price is a string, convert to numeric
  150 |             expectedNumeric = parseInt(expectedPrice.replace(/[^0-9]/g, ''), 10);
  151 |         } else {
  152 |             expectedNumeric = expectedPrice;
  153 |         }
  154 |         
  155 |         const actualNumeric = await this.getMinPriceValue();
  156 |         expect(actualNumeric).toBe(expectedNumeric);
  157 |     }
  158 |     
  159 |     /**
  160 |      * Verify the maximum price is set to the expected value
  161 |      * @param expectedPrice Expected price value (number or formatted string)
  162 |      */
  163 |     async verifyMaxPrice(expectedPrice: string | number): Promise<void> {
  164 |         let expectedNumeric: number;
  165 |         
  166 |         if (typeof expectedPrice === 'string') {
  167 |             // If expected price is a string, convert to numeric
  168 |             expectedNumeric = parseInt(expectedPrice.replace(/[^0-9]/g, ''), 10);
  169 |         } else {
  170 |             expectedNumeric = expectedPrice;
  171 |         }
  172 |         
  173 |         const actualNumeric = await this.getMaxPriceValue();
  174 |         expect(actualNumeric).toBe(expectedNumeric);
  175 |     }
  176 |     
  177 |     /**
  178 |      * Select a property type
  179 |      * @param propertyType The property type to select
  180 |      */
  181 |     async selectPropertyType(propertyType: string): Promise<void> {
  182 |         await this.propertyTypeDropdown.click();
  183 |         await this.select2ResultsOption.getByText(propertyType, { exact: false }).click();
  184 |     }
  185 |      
  186 |     /**
  187 |      * Perform search with the current filter settings
```