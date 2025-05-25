# Test info

- Name: Type of user: Client >> MW Menu: Design >> Sub-menu: Settings >> Sub-menu: Global >> Set Map, Great Schools and Walk Score in Details Global Settings and verify in FE page - User: engage_new
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/settings/detailsGlobalPreferences.spec.ts:15:29

# Error details

```
Error: Timed out 20000ms waiting for expect(locator).toBeVisible()

Locator: locator('#IDX-walkscoreContainer')
Expected: visible
Received: <element(s) not found>
Call log:
  - expect.toBeVisible with timeout 20000ms
  - waiting for locator('#IDX-walkscoreContainer')

    at FrontEndDetailsPage.verifyWalkScoreVisible (/opt/atlassian/pipelines/agent/build/tests/pages/client/frontEndPages/FrontEndDetailsPage.ts:102:43)
    at /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/settings/detailsGlobalPreferences.spec.ts:28:62
```

# Page snapshot

```yaml
- text: "{\"message\":\"failure to get a peer from the ring-balancer\"}"
```

# Test source

```ts
   2 | import { BasePage } from '../../BasePage';
   3 | import { waitForPageToBeFullyLoaded } from '../../../utils/page-utils';
   4 | //import { waitForPageToBeFullyLoaded } from '../../../utils/page-utils';
   5 |
   6 | export class FrontEndDetailsPage extends BasePage {
   7 |   // Page header elements
   8 |   private readonly addressStreet: Locator;
   9 |   private readonly addressRegion: Locator;
   10 |
   11 |   // Action buttons
   12 |   private readonly savePropertyButton: Locator;
   13 |   private readonly printFlyerButton: Locator;
   14 |   private readonly photoGalleryLink: Locator;
   15 |   private readonly mortgageCalculatorButton: Locator;
   16 |   private readonly mapButton: Locator;
   17 |   private readonly moreInfoButton: Locator;
   18 |   private readonly getDirectionsButton: Locator;
   19 |
   20 |   // Tab panels
   21 |   private readonly basicInfoPanel: Locator;
   22 |   private readonly walkScorePanel: Locator;
   23 |   private readonly schoolsPanel: Locator;
   24 |   private readonly additionalInfoPanel: Locator;
   25 |   private readonly primaryFeaturesPanel: Locator;
   26 |
   27 |   // Map elements
   28 |   private readonly mapContainer: Locator;
   29 |   private readonly mapModal: Locator;
   30 |   private readonly mapCloseButton: Locator;
   31 |   private readonly mapView: Locator;
   32 |   private readonly mapControls: Locator;
   33 |
   34 |   // Walk Score and GreatSchools elements - Updated based on actual structure
   35 |   private readonly walkScoreContainer: Locator;
   36 |   private readonly walkScoreTileDiv: Locator;
   37 |   private readonly walkScoreIframe: Locator;
   38 |   private readonly greatSchoolsWidget: Locator;
   39 |   private readonly greatSchoolsIframe: Locator;
   40 |
   41 |   /**
   42 |    * Constructor initializes all page elements
   43 |    * @param page Playwright page object
   44 |    */
   45 |   constructor(page: Page) {
   46 |     super(page);
   47 |
   48 |     // Page header elements
   49 |     this.addressStreet = page.locator('#IDX-detailsAddressStreet');
   50 |     this.addressRegion = page.locator('#IDX-detailsAddressRegion');
   51 |
   52 |     // Action buttons
   53 |     this.savePropertyButton = page.locator('#IDX-saveProperty');
   54 |     this.printFlyerButton = page.locator('#IDX-printable');
   55 |     this.photoGalleryLink = page.locator('#IDX-detailsPhotoGalleryLink');
   56 |     this.mortgageCalculatorButton = page.locator('#IDX-detailsDescriptionActionsMortgageLink');
   57 |     this.mapButton = page.locator('#IDX-detailsDescriptionActionsMap');
   58 |     this.moreInfoButton = page.locator('#IDX-detailsDescriptionActionsMoreInfo');
   59 |     this.getDirectionsButton = page.locator('#IDX-detailsDescriptionActionsDirections');
   60 |
   61 |     // Tab panels
   62 |     this.basicInfoPanel = page.locator('#IDX-detailsBasicInfo');
   63 |     this.walkScorePanel = page.locator('#IDX-detailsWalkScoreBefore');
   64 |     this.schoolsPanel = page.locator('#IDX-detailsContainer-greatSchools');
   65 |     this.additionalInfoPanel = page.locator('#IDX-detailsContainer-b001--2');
   66 |     this.primaryFeaturesPanel = page.locator('#IDX-detailsContainer-b001--1');
   67 |
   68 |     // Map elements
   69 |     this.mapContainer = page.locator('#IDX-detailsMap');
   70 |     this.mapModal = page.locator('#IDX-mapContainer');
   71 |     this.mapCloseButton = page.locator('#IDX-mapContainer .IDX-modal__close');
   72 |     this.mapView = page.locator('#IDX-map');
   73 |     this.mapControls = page.locator('.leaflet-control-container');
   74 |
   75 |     // Walk Score and GreatSchools elements
   76 |     this.walkScoreContainer = page.locator('#IDX-walkscoreContainer');
   77 |     this.walkScoreTileDiv = page.locator('#ws-walkscore-tile');
   78 |     this.walkScoreIframe = page.locator('#ws-walkscore-tile iframe');
   79 |     this.greatSchoolsWidget = page.locator('#gsWidget');
   80 |     this.greatSchoolsIframe = page.locator('#gsWidget iframe');
   81 |   }
   82 |
   83 |   /**
   84 |    * Navigate to a specific listing details page
   85 |    * @param idxID MLS ID
   86 |    * @param listingID Listing ID
   87 |    */
   88 |   async goto(idxID: string, listingID: string): Promise<void> {
   89 |     await this.page.goto(`${this.envConfig.MW_BASE_URL}/idx/details/listing/${idxID}/${listingID}`);
   90 |   }
   91 |
   92 |   /**
   93 |    * Verify that Walk Score widget is visible
   94 |    * This checks for the Walk Score elements without relying on specific content
   95 |    */
   96 |   async verifyWalkScoreVisible(): Promise<void> {
   97 |     // Make sure the Walk Score panel is expanded
   98 |     const walkScorePanelHeading = this.walkScorePanel.locator('.IDX-panel-heading');
   99 |     //await walkScorePanelHeading.click();
  100 |     
  101 |     // Check for the Walk Score container
> 102 |     await expect(this.walkScoreContainer).toBeVisible();
      |                                           ^ Error: Timed out 20000ms waiting for expect(locator).toBeVisible()
  103 |     
  104 |     // Check for the Walk Score tile div
  105 |     await expect(this.walkScoreTileDiv).toBeVisible();
  106 |     
  107 |     // Check for the Walk Score iframe
  108 |     await expect(this.walkScoreIframe).toBeVisible();
  109 |   }
  110 |
  111 | /**
  112 |  * Verify that GreatSchools widget is visible
  113 |  * This checks for the GreatSchools iframe and its content
  114 |  */
  115 | async verifyGreatSchoolsVisible(): Promise<void> {
  116 |   // 1. Verify the schools panel exists
  117 |   await expect(this.schoolsPanel).toBeVisible();
  118 |   /*
  119 |   // 2. Check if the panel is expanded by checking the aria-expanded attribute
  120 |   const isExpanded = await this.schoolsPanel
  121 |     .locator('.IDX-panel-collapse-toggle')
  122 |     .getAttribute('aria-expanded')
  123 |     .then(value => value === 'true');
  124 |   
  125 |   // 3. If panel is not expanded, click to expand it
  126 |   if (!isExpanded) {
  127 |     const schoolsPanelHeading = this.schoolsPanel.locator('.IDX-panel-heading');
  128 |     await schoolsPanelHeading.click();
  129 |     
  130 |     // Add a small wait to allow animation to complete
  131 |     await this.page.waitForTimeout(500);
  132 |   }
  133 |   */
  134 |   // 4. Now check for the iframe and its content
  135 |   const greatSchoolsIframe = this.page.locator('#gsWidget iframe');
  136 |   await expect(greatSchoolsIframe).toBeVisible({ timeout: 10000 });
  137 |   
  138 |   // 5. Additional verification of content inside iframe
  139 |   const frameLocator = this.page.frameLocator('#gsWidget iframe');
  140 |   try {
  141 |     await expect(frameLocator.locator('body')).toBeVisible({ timeout: 5000 });
  142 |     
  143 |     // Verify there's actual content in the iframe
  144 |     const iframeContentExists = await frameLocator.locator('div').count();
  145 |     expect(iframeContentExists).toBeGreaterThan(0);
  146 |   } catch (error) {
  147 |     throw new Error(`GreatSchools iframe content not found or not properly loaded: ${error}`);
  148 |   }
  149 | }
  150 |
  151 |   /**
  152 |    * Verify that Map button is present
  153 |    */
  154 |   async verifyMapButtonVisible(): Promise<void> {
  155 |     await expect(this.mapButton).toBeVisible();
  156 |   }
  157 |
  158 |   /**
  159 |    * Open the map modal
  160 |    */
  161 |   async openMap(): Promise<void> {
  162 |     await this.mapButton.click();
  163 |     await expect(this.mapModal).toBeVisible();
  164 |   }
  165 |
  166 | /**
  167 |  * Verify map is displayed with controls
  168 |  */
  169 | async verifyMapDisplayed(): Promise<void> {
  170 |   // 1. Open the map modal
  171 |   await this.openMap();
  172 |   
  173 |   // 2. Check that the map view is visible
  174 |   await expect(this.mapView).toBeVisible();
  175 |   
  176 |   // 3. Wait for Leaflet to initialize
  177 |   // Add a small delay to allow the map controls to become visible
  178 |   await waitForPageToBeFullyLoaded(this.page);
  179 |   await this.page.waitForTimeout(1000);
  180 |   
  181 |   // 4. Check for Leaflet map controls using a more specific selector
  182 |   const zoomControls = this.page.locator('.leaflet-control-zoom');
  183 |   await expect(zoomControls).toBeVisible({ timeout: 30000 });
  184 |   
  185 |   // 5. Verify the zoom in button is present (more specific than checking the container)
  186 |   const zoomInButton = this.page.locator('.leaflet-control-zoom-in');
  187 |   await expect(zoomInButton).toBeVisible();
  188 |   
  189 |   // 6. Verify the layers control is present
  190 |   const layersControl = this.page.locator('.leaflet-control-layers');
  191 |   await expect(layersControl).toBeVisible();
  192 | }
  193 |   
  194 | }
```