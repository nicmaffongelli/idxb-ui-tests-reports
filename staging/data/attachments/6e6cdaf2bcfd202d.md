# Test info

- Name: User: Client-Core-1-Existing >> Client can perform a search in Address Search FE page and the number of results is 25 - User: Client-Core-1-Existing
- Location: /opt/atlassian/pipelines/agent/build/src/tests/specs/clients/06_design/04_settings/01_global/resultsGlobalPreferences.spec.ts:22:13

# Error details

```
TimeoutError: page.goto: Timeout 20000ms exceeded.
Call log:
  - navigating to "https://1747064226435.idxstaging.com/idx/search/address", waiting until "load"

    at FrontEndAddressSearchPage.goto (/opt/atlassian/pipelines/agent/build/src/page-objects/client/frontEndPages/FrontEndAddressSearchPage.ts:40:21)
    at /opt/atlassian/pipelines/agent/build/src/tests/specs/clients/06_design/04_settings/01_global/resultsGlobalPreferences.spec.ts:23:52
```

# Test source

```ts
   1 | import { Page, Locator, expect, BasePage, waitForPageToBeFullyLoaded } from '@shared-client-imports';
   2 |
   3 | export class FrontEndAddressSearchPage extends BasePage {
   4 |   // Search form elements
   5 |   private readonly searchButton: Locator;
   6 |
   7 |   // Results page elements
   8 |   private readonly listingCardImageOverlays: Locator; // Used to count results
   9 |   private readonly listingCardImageOverlaySelector: Locator; // Selector for waiting
  10 |
  11 |   // Address search page container
  12 |   private readonly addressSearchPageContainer: Locator;
  13 |   private readonly navigationButtonsBar: Locator;
  14 |   private readonly actionsButtons: Locator;
  15 |
  16 |   /**
  17 |    * Constructor initializes all page elements
  18 |    * @param page Playwright page object
  19 |    */
  20 |   constructor(page: Page) {
  21 |     super(page);
  22 |
  23 |     // Search form elements
  24 |     this.searchButton = page.locator('#IDX-formSubmit');
  25 |
  26 |     // Results page elements
  27 |     this.listingCardImageOverlays = page.locator('.idx-listing-card__image-overlay');
  28 |     this.listingCardImageOverlaySelector = page.locator('.idx-listing-card__image-overlay');
  29 |
  30 |     // Address search page container
  31 |     this.addressSearchPageContainer = page.locator('#IDX-searchPageWrapper');
  32 |     this.navigationButtonsBar = page.getByRole('navigation');
  33 |     this.actionsButtons = page.locator('#IDX-action-buttons');
  34 |   }
  35 |
  36 |   /**
  37 |    * Navigate to the Address Search page
  38 |    */
  39 |   async goto(userSubdomain: string): Promise<void> {
> 40 |     await this.page.goto(`https://${userSubdomain}.${this.globalAndEnvironmentVariables.URL_ENV_PART}.com/idx/search/address`);
     |                     ^ TimeoutError: page.goto: Timeout 20000ms exceeded.
  41 |   }
  42 |
  43 |   /**
  44 |    * Perform search with current criteria
  45 |    */
  46 |   async performSearch(): Promise<void> {
  47 |     await this.searchButton.click();
  48 |     await waitForPageToBeFullyLoaded(this.page);
  49 |   }
  50 |
  51 |   /**
  52 |    * Count the number of listings on the results page
  53 |    * @returns The number of listings displayed
  54 |    */
  55 |   async countListings(): Promise<number> {
  56 |     await this.listingCardImageOverlaySelector.waitFor();
  57 |     const count = await this.listingCardImageOverlays.count();
  58 |     return count;
  59 |   }
  60 |
  61 |   /**
  62 |    * Verify that the number of results matches the expected count
  63 |    * @param expectedCount The expected number of results
  64 |    */
  65 |   async verifyResultCount(expectedCount: number): Promise<void> {
  66 |     const actualCount = await this.countListings();
  67 |     expect(actualCount).toBe(expectedCount);
  68 |   }
  69 |
  70 |   /*
  71 |   * Get the address search page container
  72 |   * @returns The address search page container
  73 |   */
  74 |   async getAddressSearchPageContainer(): Promise<Locator> {
  75 |     return this.addressSearchPageContainer;
  76 |   }
  77 |
  78 |   /*
  79 |   * Get the navigation buttons bar
  80 |   * @returns The navigation buttons bar
  81 |   */
  82 |   async getNavigationButtonsBar(): Promise<Locator> {
  83 |     return this.navigationButtonsBar;
  84 |   }
  85 |
  86 |   /*
  87 |   * Get the actions buttons
  88 |   * @returns The actions buttons
  89 |   */
  90 |   async getActionsButtons(): Promise<Locator> {
  91 |     return this.actionsButtons;
  92 |   }
  93 | }
```