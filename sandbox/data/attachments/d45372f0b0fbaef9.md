# Test info

- Name: Create a new supplemental listing and then delete it for each user >> Create Supplemental Listing - User: Client-Engage-1-Existing
- Location: /opt/atlassian/pipelines/agent/build/src/tests/specs/clients/03_listings/addSupplementalListing.spec.ts:11:13

# Error details

```
TimeoutError: locator.selectOption: Timeout 20000ms exceeded.
Call log:
  - waiting for getByLabel('Select MLS')
    - locator resolved to <select id="idxID" class="span4" name="likeIdxID">…</select>
  - attempting select option action
    2 × waiting for element to be visible and enabled
      - element is not visible
    - retrying select option action
    - waiting 20ms
    2 × waiting for element to be visible and enabled
      - element is not visible
    - retrying select option action
      - waiting 100ms
    39 × waiting for element to be visible and enabled
       - element is not visible
     - retrying select option action
       - waiting 500ms

    at AddSupplementalListingPage.addListingWithDefaultValues (/opt/atlassian/pipelines/agent/build/src/page-objects/client/03_listings/AddSupplementalListingPage.ts:137:32)
    at /opt/atlassian/pipelines/agent/build/src/tests/specs/clients/03_listings/addSupplementalListing.spec.ts:17:65
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
   37 |     readonly partialBathsInput: Locator;
   38 |     readonly acresInput: Locator;
   39 |     readonly sqFtInput: Locator;
   40 |     readonly yearBuiltInput: Locator;
   41 |     readonly zoningInput: Locator;
   42 |     readonly remarksInput: Locator;
   43 |     
   44 |     // Additional fields
   45 |     readonly interiorFeaturesInput: Locator;
   46 |     readonly exteriorFeaturesInput: Locator;
   47 |     readonly areaInput: Locator;
   48 |     readonly neighborhoodInput: Locator;
   49 |     readonly subdivisionInput: Locator;
   50 |     readonly financialInput: Locator;
   51 |     readonly styleInput: Locator;
   52 |     readonly rentLeaseSelector: Locator;
   53 |     readonly customLinkTextInput: Locator;
   54 |     readonly customLinkURLInput: Locator;
   55 |     
   56 |     // Form actions
   57 |     readonly addPropertyButton: Locator;
   58 |     
   59 |     // Success notification
   60 |     readonly successNotification: Locator;
   61 |     
   62 |     /**
   63 |      * Constructor for AddListingPage
   64 |      * @param page - Playwright page object
   65 |      */
   66 |     constructor(page: Page) {
   67 |         super(page);
   68 |         
   69 |         // Basic form fields
   70 |         this.mlsSelector = page.getByLabel('Select MLS');
   71 |         this.propertyTypeSelector = page.getByLabel('Select Property Type');
   72 |         this.propertySubTypeSelector = page.getByLabel('Property Sub Type');
   73 |         this.agentSelector = page.getByLabel('Agent');
   74 |         
   75 |         // Address fields
   76 |         this.streetNumberInput = page.getByRole('textbox', { name: 'Street Number' });
   77 |         this.streetDirectionInput = page.getByRole('textbox', { name: 'Street Direction' });
   78 |         this.streetNameInput = page.getByRole('textbox', { name: 'Street Name' });
   79 |         this.unitNumberInput = page.getByRole('textbox', { name: 'Unit Number' });
   80 |         this.cityNameInput = page.getByRole('textbox', { name: 'City' });
   81 |         this.countyNameInput = page.getByRole('textbox', { name: 'County' });
   82 |         this.stateSelector = page.getByLabel('State');
   83 |         this.zipcodeInput = page.getByRole('textbox', { name: 'Postal Code*' });
   84 |         this.zip4Input = page.getByRole('textbox', { name: 'Postal Code + 4' });
   85 |         
   86 |         // Property details
   87 |         this.statusSelector = page.getByLabel('Status');
   88 |         this.listingPriceInput = page.getByRole('textbox', { name: 'Listing Price' });
   89 |         this.rentLeasePriceInput = page.getByRole('textbox', { name: 'Rent/Lease Price' });
   90 |         this.offSeasonPriceInput = page.getByRole('textbox', { name: 'Off Season Price' });
   91 |         this.soldPriceInput = page.getByRole('textbox', { name: 'Sold Price' });
   92 |         this.soldDateInput = page.getByRole('textbox', { name: 'Sold Date' });
   93 |         
   94 |         // Property specifications
   95 |         this.bedroomsInput = page.getByRole('textbox', { name: 'Bedrooms' });
   96 |         this.totalBathsInput = page.getByRole('textbox', { name: 'Total Bathrooms' });
   97 |         this.fullBathsInput = page.getByRole('textbox', { name: 'Full Bathrooms' });
   98 |         this.partialBathsInput = page.getByRole('textbox', { name: 'Partial Bathrooms' });
   99 |         this.acresInput = page.getByRole('textbox', { name: 'Acres' });
  100 |         this.sqFtInput = page.getByRole('textbox', { name: 'Square Feet' });
  101 |         this.yearBuiltInput = page.getByRole('textbox', { name: 'Year Built' });
  102 |         this.zoningInput = page.getByRole('textbox', { name: 'Zoning' });
  103 |         this.remarksInput = page.getByRole('textbox', { name: 'Remarks' });
  104 |         
  105 |         // Additional fields
  106 |         this.interiorFeaturesInput = page.getByRole('textbox', { name: 'Interior Features' });
  107 |         this.exteriorFeaturesInput = page.getByRole('textbox', { name: 'Exterior Features' });
  108 |         this.areaInput = page.getByRole('textbox', { name: 'Area' });
  109 |         this.neighborhoodInput = page.getByRole('textbox', { name: 'Neighborhood' });
  110 |         this.subdivisionInput = page.getByRole('textbox', { name: 'Subdivision' });
  111 |         this.financialInput = page.getByRole('textbox', { name: 'Financial' });
  112 |         this.styleInput = page.getByRole('textbox', { name: 'Style' });
  113 |         this.rentLeaseSelector = page.getByLabel('Rent/Lease');
  114 |         this.customLinkTextInput = page.getByRole('textbox', { name: 'Custom Link Text' });
  115 |         this.customLinkURLInput = page.getByRole('textbox', { name: 'Custom Link URL' });
  116 |         
  117 |         // Form actions
  118 |         this.addPropertyButton = page.getByRole('button', { name: 'Add Property' });
  119 |         
  120 |         // Success notification
  121 |         this.successNotification = page.locator('#jGrowl');
  122 |     }
  123 |     
  124 |     /**
  125 |      * Go directly to the add listing page
  126 |      */
  127 |     async goto() {
  128 |         await this.page.goto(this.globalAndEnvironmentVariables.MW_BASE_URL + '/mgmt/listings/create');
  129 |         await waitForPageToBeFullyLoaded(this.page);
  130 |     }
  131 |     
  132 |     /**
  133 |      * Add a listing with default test values
  134 |      */
  135 |     async addListingWithDefaultValues() {
  136 |         // Select MLS and Property Type
> 137 |         await this.mlsSelector.selectOption('b001');
      |                                ^ TimeoutError: locator.selectOption: Timeout 20000ms exceeded.
  138 |         await waitForPageToBeFullyLoaded(this.page);
  139 |         await this.propertySubTypeSelector.selectOption('Single Family Residence');
  140 |         
  141 |         // Fill Address Details
  142 |         await this.streetNumberInput.fill('3562');
  143 |         await this.streetDirectionInput.fill('SE');
  144 |         await this.streetNameInput.fill('Harrison St');
  145 |         await this.cityNameInput.fill('Portland');
  146 |         await this.countyNameInput.fill('Oregon');
  147 |         await this.stateSelector.selectOption('Oregon');
  148 |         await this.zipcodeInput.fill('97214');
  149 |         
  150 |         // Fill Pricing Details
  151 |         await this.listingPriceInput.fill('1500000');
  152 |         await this.rentLeasePriceInput.fill('5000');
  153 |         await this.offSeasonPriceInput.fill('3000');
  154 |         
  155 |         // Fill Property Specifications
  156 |         await this.bedroomsInput.fill('5');
  157 |         await this.totalBathsInput.fill('4');
  158 |         await this.fullBathsInput.fill('3');
  159 |         await this.partialBathsInput.fill('1');
  160 |         await this.sqFtInput.fill('4000');
  161 |         await this.yearBuiltInput.fill('2010');
  162 |         await this.remarksInput.fill('Amazing location');
  163 |         
  164 |         // Fill Additional Details
  165 |         await this.interiorFeaturesInput.fill('HotTub, pool, grass');
  166 |         await this.exteriorFeaturesInput.fill('Garage, air conditioning');
  167 |         await this.areaInput.fill('sheldon');
  168 |         await this.neighborhoodInput.fill('sheldon neighborhood');
  169 |         await this.subdivisionInput.fill('subdivision');
  170 |         
  171 |         // Submit the form
  172 |         await this.addPropertyButton.click();
  173 |         
  174 |         // Verify success
  175 |         await expect(this.successNotification).toContainText('Your new supplemental property has been added.');
  176 |     }
  177 | }
```