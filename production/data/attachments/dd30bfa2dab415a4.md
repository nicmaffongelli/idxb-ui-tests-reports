# Test info

- Name: Type of user: Client >> MW Menu: Design >> Sub-menu: Widgets >> Sub-menu: Legacy >> Create Showcase Legacy Widget with Custom Search - User: Client-Elite-1-Existing
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/widgets/legacyWidgets.spec.ts:20:25

# Error details

```
TimeoutError: page.click: Timeout 20000ms exceeded.
Call log:
  - waiting for locator('div.select2-result-label:has-text("Portland")')

    at AddLegacyWidgetPage.enterCity (/opt/atlassian/pipelines/agent/build/tests/pages/client/design/widgets/AddLegacyWidgetPage.ts:293:25)
    at AddLegacyWidgetPage.createShowcaseWidgetWithCustomSearch (/opt/atlassian/pipelines/agent/build/tests/pages/client/design/widgets/AddLegacyWidgetPage.ts:391:13)
    at /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/widgets/legacyWidgets.spec.ts:27:25
```

# Page snapshot

```yaml
- navigation:
  - link "IDX Broker":
    - /url: /mgmt/dashboard
    - img "IDX Broker"
  - list:
    - listitem:
      - text: Live
      - strong: "Signed in as:"
      - text: Mimi (60786)
    - listitem:
      - text: "1"
      - img
- text: Notifications
- button "Clear All"
- text: SSL Upgrade Complete Your site is now SSL compatible. You may now update your IDX page links and Widgets.
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
    - listitem: Design -
    - listitem: Account +
    - listitem: Support +
- listitem:
  - link "Page Help":
    - /url: "#"
- heading "Add Widget" [level=1]
- link "View All":
  - /url: /mgmt/widgets
- heading "Build a widget" [level=3]
- paragraph: Choose the basic options for creating a widget.
- button "Showcase" [disabled]
- button "Custom Search" [disabled]
- link "Advanced Search":
  - /url: javascript:void(0)
- button "Advanced Search" [disabled]
- combobox [disabled]:
  - option
  - option "Address"
  - option "Advanced Search" [selected]
  - option "Basic Search"
  - option "Email Update Signup"
  - option "Listing ID"
  - option "AI Smart Search"
- text: 1 Properties to feature based on results Select Market Area
- link "Texas MLS":
  - /url: javascript:void(0)
- text: Select Market Area
- button "Texas MLS"
- combobox "Select Market Area":
  - option
  - option "Texas MLS" [selected]
  - option "Regional Multiple Listing Service"
- text: Property Type
- link "Residential":
  - /url: javascript:void(0)
- text: Property Type
- button "Residential"
- combobox "Property Type":
  - option
  - option "Residential" [selected]
  - option "Multi-Family"
  - option "Farm And Ranch"
  - option "Commercial"
  - option "Land"
- text: Property Sub Type
- list:
  - listitem:
    - text: Property Sub Type
    - textbox "Property Sub Type"
- listbox "Property Sub Type":
  - option
  - option "Barndominium"
  - option "Condominium"
  - option "Manufactured Home"
  - option "Mobile home with Land"
  - option "Single Family"
  - option "Single Family w/ Acreage"
  - option "Single Family w/ Rental"
  - option "Townhouse"
- text: Status
- list:
  - listitem:
    - text: "Status: Active"
    - link "Remove item":
      - /url: "#"
      - text: ×
  - listitem:
    - text: Status
    - textbox "Status"
- listbox "Status":
  - option
  - option "Active" [selected]
  - option "Back On Market"
  - option "Accepting Backups"
  - option "Pending with Contingency"
- text: City, County, Postal Code
- list:
  - listitem:
    - text: City, County, Postal Code
    - textbox "City, County, Postal Code": Portland
- listbox "City, County, Postal Code":
  - group:
    - option "Beaumont"
    - option "Bon Wier"
    - option "Bridge City"
    - option "Broaddus"
    - option "Bronson"
    - option "Brookeland"
    - option "Buna"
    - option "Burkeville"
    - option "Call"
    - option "Carthage"
    - option "Center"
    - option "Chester"
    - option "Colmesneil"
    - option "Corrigan"
    - option "Crockett"
    - option "Doucette"
    - option "Etoile"
    - option "Evadale"
    - option "Fred"
    - option "Garrison"
    - option "Groesbeck"
    - option "Hemphill"
    - option "Hereford"
    - option "Hillister"
    - option "Ivanhoe"
    - option "Jasper"
    - option "Joaquin"
    - option "Kirbyville"
    - option "Kountze"
    - option "Lamesa"
    - option "Livingston"
    - option "Longview"
    - option "Lufkin"
    - option "Magnolia Springs"
    - option "Marquez"
    - option "Mexia"
    - option "Milam"
    - option "Muleshoe"
    - option "Nacogdoches"
    - option "Newton"
    - option "Onalaska"
    - option "Orange"
    - option "Pineland"
    - option "Quanah"
    - option "San Augustine"
    - option "Shelbyville"
    - option "Shepherd"
    - option "Spurger"
    - option "Tenaha"
    - option "Timpson"
    - option "Trinity"
    - option "Vidor"
    - option "Village Mills"
    - option "Warren"
    - option "Wiergate"
    - option "Woodville"
    - option "Zavalla"
  - group:
    - option "Angelina"
    - option "Bailey"
    - option "Dawson"
    - option "Deaf Smith"
    - option "Gregg"
    - option "Hardeman"
    - option "Hardin"
    - option "Hemphill"
    - option "Houston"
    - option "Jasper"
    - option "Jefferson"
    - option "Leon"
    - option "Limestone"
    - option "Nacogdoches"
    - option "Newton"
    - option "Orange"
    - option "Other"
    - option "Panola"
    - option "Polk"
    - option "Sabine"
    - option "San Augustine"
    - option "San Jacinto"
    - option "Shelby"
    - option "Trinity"
    - option "Tyler"
  - group:
    - option "75605"
    - option "75633"
    - option "75835"
    - option "75846"
    - option "75862"
    - option "75901"
    - option "75904"
    - option "75928"
    - option "75929"
    - option "75930"
    - option "75931"
    - option "75932"
    - option "75935"
    - option "75936"
    - option "75938"
    - option "75939"
    - option "75942"
    - option "75944"
    - option "75946"
    - option "75948"
    - option "75951"
    - option "75953"
    - option "75954"
    - option "75956"
    - option "75959"
    - option "75964"
    - option "75966"
    - option "75968"
    - option "75972"
    - option "75973"
    - option "75974"
    - option "75975"
    - option "75977"
    - option "75979"
    - option "75980"
    - option "76642"
    - option "76667"
    - option "76968"
    - option "77351"
    - option "77360"
    - option "77371"
    - option "77611"
    - option "77612"
    - option "77615"
    - option "77616"
    - option "77624"
    - option "77625"
    - option "77632"
    - option "77660"
    - option "77662"
    - option "77663"
    - option "77664"
    - option "77708"
    - option "77865"
    - option "79045"
    - option "79252"
    - option "79331"
    - option "79347"
- text: Min Price
- 'link "Min Price: $200,000"':
  - /url: javascript:void(0)
- text: Min Price
- 'button "Min Price: $200,000"'
- textbox "Min Price": "200000"
- text: Max Price
- 'link "Max Price: $800,000"':
  - /url: javascript:void(0)
- text: Max Price
- 'button "Max Price: $800,000"'
- textbox "Max Price": "800000"
- text: Bedrooms
- link "Bedrooms":
  - /url: javascript:void(0)
- text: Bedrooms
- button "Bedrooms"
- combobox "Bedrooms":
  - option [selected]
  - option "Any Number"
  - option "Studio"
  - option "1+"
  - option "2+"
  - option "3+"
  - option "4+"
  - option "5+"
  - option "6+"
  - option "7+"
  - option "8+"
  - option "9+"
  - option "10+"
- text: Bathrooms
- link "Bathrooms":
  - /url: javascript:void(0)
- text: Bathrooms
- button "Bathrooms"
- combobox "Bathrooms":
  - option [selected]
  - option "Any Number"
  - option "1+"
  - option "2+"
  - option "3+"
  - option "4+"
  - option "5+"
  - option "6+"
  - option "7+"
  - option "8+"
  - option "9+"
  - option "10+"
- text: SqFt
- link "SqFt":
  - /url: javascript:void(0)
- text: SqFt
- button "SqFt"
- textbox "SqFt"
- text: Acres
- link "Acres":
  - /url: javascript:void(0)
- text: Acres
- button "Acres"
- textbox "Acres"
- text: Price Reduction
- link "Price Reduced":
  - /url: javascript:void(0)
- text: Price Reduction
- button "Price Reduced"
- combobox "Price Reduction":
  - option [selected]
  - option "In the last day"
  - option "In the last 3 days"
  - option "In the last 7 days"
  - option "In the last 2 weeks"
  - option "In the last month"
- text: Max Days Listed
- link "Max Days Listed":
  - /url: javascript:void(0)
- text: Max Days Listed
- button "Max Days Listed"
- textbox "Max Days Listed"
- text: Refinement
- list:
  - listitem:
    - text: Refinement
    - textbox "Refinement": Image, Virtual Tour, Virtual Open House, Open House, Featured
- listbox "Refinement":
  - option "Has Image"
  - option "Has Virtual Tour"
  - option "Has Open House"
  - option "Has Virtual Open House"
  - option "Featured Listings"
- text: Results per page
- link "Results per page":
  - /url: javascript:void(0)
- text: Results per page
- button "Results per page"
- combobox "Results per page":
  - option [selected]
  - option "5"
  - option "10"
  - option "25"
  - option "50"
  - option "100"
- button "Reset"
- button "View Results in New Window"
- text: Elementary School
- listbox "Elementary School":
  - option "BISD"
  - option "Beaumont"
  - option "Broaddus"
  - option "Broaddus ISD"
  - option "Brookeland"
  - option "Brookeland ISD"
  - option "Brookhollow Elementary"
  - option "Brookland ISD"
  - option "Burkeville"
  - option "Burkeville Elementary"
  - option "Burkeville ISD"
  - option "CENTER ISD"
  - option "Center"
  - option "Dillman & DeShazo"
  - option "Evadale"
  - option "Garrison"
  - option "HISD"
  - option "Hardin-Jefferson"
  - option "Hemphill"
  - option "Hemphill ISD"
  - option "Hemphill School Dist."
  - option "Hemphill School District"
  - option "JISD"
  - option "Jasper"
  - option "Jasper ISD"
  - option "Joaquin"
  - option "Joaquin ISD"
  - option "Kirbyville"
  - option "Kirbyville CISD"
  - option "Kirbyville ISD"
  - option "Lufkin ISD"
  - option "NISD"
  - option "Newton"
  - option "Newton ISD"
  - option "Pine Tree ISD"
  - option "Pineland"
  - option "SAISD"
  - option "San Augustine"
  - option "San Augustine Elementary"
  - option "San Augustine ISD"
  - option "Shelbyville"
  - option "Shelbyville ISD"
  - option "Spurger"
  - option "Spurger ISD"
  - option "Timpson"
  - option "Vidor"
  - option "WARREN"
  - option "WARREN ISD"
  - option "WSISD"
  - option "West Sabine"
  - option "West Sabine ISD"
  - option "West Sabine School"
  - option "Woodville"
  - option "Zavalla ISD"
  - option "woodville isd"
- text: Junior High
- listbox "Junior High":
  - option "BISD"
  - option "Beaumont"
  - option "Broaddus"
  - option "Broaddus ISD"
  - option "Brookeland"
  - option "Brookeland ISD"
  - option "Brookland ISD"
  - option "Burkeville"
  - option "Burkeville ISD"
  - option "CENTER ISD"
  - option "Center"
  - option "Evadale"
  - option "Garrison"
  - option "HISD"
  - option "Hardin-Jefferson"
  - option "Hemphill"
  - option "Hemphill ISD"
  - option "JISD"
  - option "Jasper"
  - option "Jasper ISD"
  - option "Joaquin"
  - option "Joaquin ISD"
  - option "Kirbyville"
  - option "Kirbyville CISD"
  - option "Kirbyville ISD"
  - option "Lufkin ISD"
  - option "Lufkin Middle"
  - option "Newton"
  - option "Newton ISD"
  - option "Pine Tree ISD"
  - option "SAISD"
  - option "San Augustine"
  - option "San Augustine ISD"
  - option "San Augustine Junior High"
  - option "Shelbyville"
  - option "Shelbyville ISD"
  - option "Spurger"
  - option "Spurger ISD"
  - option "Timpson"
  - option "Vidor"
  - option "WARREN"
  - option "WARREN ISD"
  - option "WSISD"
  - option "Watson"
  - option "West Sabine"
  - option "West Sabine ISD"
  - option "West Sabine School"
  - option "Woodville"
  - option "Zavalla ISD"
  - option "woodville isd"
- text: Senior High School
- listbox "Senior High School":
  - option "BISD"
  - option "Beaumont"
  - option "Broaddus"
  - option "Broaddus ISD"
  - option "Brookeland"
  - option "Brookeland HS"
  - option "Brookeland ISD"
  - option "Brookland ISD"
  - option "Burkeville"
  - option "Burkeville ISD"
  - option "CENTER ISD"
  - option "Center"
  - option "Evadale"
  - option "Garrison"
  - option "HISD"
  - option "Hardin-Jefferson"
  - option "Hemphill"
  - option "Hemphill ISD"
  - option "JISD"
  - option "Japser ISD"
  - option "Jasper"
  - option "Jasper ISD"
  - option "Joaquin"
  - option "Joaquin ISD"
  - option "Kirbyville"
  - option "Kirbyville CISD"
  - option "Kirbyville ISD"
  - option "Lufkin High School"
  - option "Lufkin ISD"
  - option "Muleshoe"
  - option "NISD"
  - option "Newton"
  - option "Newton ISD"
  - option "Pine Tree ISD"
  - option "SAISD"
  - option "San Augustine"
  - option "San Augustine High School"
  - option "San Augustine ISD"
  - option "Shelbyville"
  - option "Shelbyville ISD"
  - option "Spurger"
  - option "Spurger ISD"
  - option "Timpson"
  - option "Vidor"
  - option "WARREN"
  - option "WARREN ISD"
  - option "WSISD"
  - option "West Sabine"
  - option "West Sabine ISD"
  - option "West Sabine School"
  - option "Woodville"
  - option "Zavalla ISD"
  - option "woodville isd"
- text: Misc Interior
- listbox "Misc Interior":
  - option "Bookcase"
  - option "Ceiling Fan"
  - option "Desk"
  - option "Hot Tub/Spa"
  - option "Pull Down Stairs"
  - option "Skylights"
  - option "Wet Bar"
  - option "Window Coverings"
- text: Remarks
- textbox "Remarks"
- text: Lot Description/Size
- listbox "Lot Description/Size":
  - option "1 to 3 Acres"
  - option "1/2 to 1 Acre"
  - option "3 to 5 Acres"
  - option "5 to 10 Acres"
  - option "10 to 20 Acres"
  - option "20 to 50 Acres"
  - option "Creek"
  - option "Lake Frontage Leased"
  - option "Lake Frontage Owned"
  - option "Less than 1/2 Acre"
  - option "More Than 50 Acres"
  - option "River Frontage"
- text: Exterior
- listbox "Exterior":
  - option "Brick"
  - option "Masonite"
  - option "Other/See Remarks"
  - option "Siding"
  - option "Stone"
  - option "Stucco"
  - option "Wood"
- text: Misc. Exterior
- listbox "Misc. Exterior":
  - option "BBQ-Grill"
  - option "Circular Drive"
  - option "Covered Patio"
  - option "Fenced"
  - option "Hot Tub/Spa"
  - option "Landscaped"
  - option "Patio"
  - option "Pool Above Ground"
  - option "Pool In Ground"
  - option "RV Parking"
  - option "Sprinkler System"
  - option "Storage Shed"
  - option "Workshop"
- text: Fireplace
- textbox "Min Fireplace"
- text: to
- textbox "Max Fireplace"
- text: Garage Type
- listbox "Garage Type":
  - option "1 Attach"
  - option "1 Carport"
  - option "1 Detach"
  - option "2 Attach"
  - option "2 Carports"
  - option "2 Detach"
  - option "3 or More Attach"
  - option "Converted"
  - option "None"
- text: Widget Options showcase v1.006 Responsive
- radio "No"
- text: "No"
- radio "Yes" [checked]
- text: Yes Widget Name*
- textbox
- text: Sorting Order*
- combobox:
  - option "Newest Listings" [selected]
  - option "Oldest Listings"
  - option "Least Expensive to Most"
  - option "Most Expensive to Least"
  - option "Bedrooms (Low to High)"
  - option "Bedrooms (High to Low)"
  - option "Square Feet (Low to High)"
  - option "Square Feet (High to Low)"
  - option "Bathrooms (Low to High)"
  - option "Bathrooms (High to Low)"
- text: Width*
- textbox [disabled]: "100"
- text: "% # Rows"
- combobox "# Rows" [disabled]:
  - option "1"
  - option "2"
  - option "#" [selected]
  - option "4"
  - option "5"
  - option "6"
  - option "7"
  - option "8"
  - option "9"
  - option "10"
- text: "# Columns"
- combobox "# Columns":
  - option "1"
  - option "2"
  - option "3" [selected]
  - option "4"
  - option "5"
  - option "6"
  - option "7"
  - option "8"
  - option "9"
  - option "10"
- text: "# Listings*"
- textbox "# Listings*": "100"
- text: Open Widget Links in a New Window
- radio "No" [checked]
- text: "No"
- radio "Yes"
- text: Yes Display View All Results Link
- radio "No" [checked]
- text: "No"
- radio "Yes"
- text: "Yes"
- button "Build Widget"
- text: "2"
- paragraph:
  - text: Services © 2025
  - link "IDX Broker":
    - /url: https://www.idxbroker.com
  - text: . All rights reserved.
- status: Advanced Search
- status
- status
- status
- status: 4 results are available, use up and down arrow keys to navigate.
- status: No matches found
- status
- status
- status
- status
- status
- status
- status
- status
- status
- status
- status
- list:
  - listitem: No matches found
```

# Test source

```ts
  193 |                 await this.supplementalPropSet.click();
  194 |                 break;
  195 |             case 'featuredSupplemental':
  196 |                 await this.featuredSupplementalPropSet.click();
  197 |                 break;
  198 |             case 'agent':
  199 |                 await this.agentPropSet.click();
  200 |                 break;
  201 |             case 'soldPending':
  202 |                 await this.soldPendingPropSet.click();
  203 |                 break;
  204 |             case 'customSearch':
  205 |                 await this.customSearchPropSet.click();
  206 |                 break;
  207 |             case 'customList':
  208 |                 await this.customListPropSet.click();
  209 |                 break;
  210 |             case 'polygonSearch':
  211 |                 await this.polygonSearchPropSet.click();
  212 |                 break;
  213 |             case 'copyAndPaste':
  214 |                 await this.copyAndPastePropSet.click();
  215 |                 break;
  216 |         }
  217 |         
  218 |         await waitForPageToBeFullyLoaded(this.page);
  219 |     }
  220 |     
  221 |     /**
  222 |      * Select a search page (used with customSearch property set)
  223 |      * @param searchPageName - Name of the search page to select
  224 |      */
  225 |     async selectSearchPage(searchPageName: 'Advanced Search' | 'Basic Search' | 'Address' | 'Listing ID' | 'Email Update Signup') {
  226 |         // Wait for the search page selector to be visible
  227 |         await this.searchPageSelector.click({ force: true });
  228 |         await waitForPageToBeFullyLoaded(this.page);
  229 |         
  230 |         // Select by search page name
  231 |         switch (searchPageName) {
  232 |             case 'Advanced Search':
  233 |                 await this.page.locator('#select2-result-label-3').click();
  234 |                 break;
  235 |             case 'Basic Search':
  236 |                 await this.page.locator('text=Basic Search').click();
  237 |                 break;
  238 |             case 'Address':
  239 |                 await this.page.locator('text=Address').click();
  240 |                 break;
  241 |             case 'Listing ID':
  242 |                 await this.page.locator('text=Listing ID').click();
  243 |                 break;
  244 |             case 'Email Update Signup':
  245 |                 await this.page.locator('text=Email Update Signup').click();
  246 |                 break;
  247 |         }
  248 |         
  249 |         //await waitForPageToBeFullyLoaded(this.page);
  250 |     }
  251 |     
  252 |     /**
  253 |      * Select property types (used in search criteria)
  254 |      * @param propertyTypes - Array of property types to select
  255 |      */
  256 |     
  257 |     async selectPropertyTypes(propertyTypes: ('Residential' | 'Land' | 'Commercial Sale' | 'Multi Family')[]) {
  258 |         //await this.propertyTypeDropdown.click();
  259 |         await waitForPageToBeFullyLoaded(this.page);
  260 |         
  261 |         for (const propertyType of propertyTypes) {
  262 |             switch (propertyType) {
  263 |                 case 'Residential':
  264 |                     //await this.page.getByRole('link', { name: 'Residential' }).click();
  265 |                     //await this.residentialPropertyType.click();
  266 |                     break;
  267 |                 case 'Land':
  268 |                     await this.page.getByRole('link', { name: 'Land' }).click();
  269 |                     await this.landPropertyType.click();
  270 |                     break;
  271 |                 case 'Commercial Sale':
  272 |                     await this.page.getByRole('link', { name: 'Commercial Sale' }).click();
  273 |                     await this.page.locator('text=Commercial Sale').click();
  274 |                     break;
  275 |                 case 'Multi Family':
  276 |                     await this.page.getByRole('link', { name: 'Multi Family' }).click();
  277 |                     await this.page.locator('text=Multi Family').click();
  278 |                     break;
  279 |             }
  280 |         }
  281 |         
  282 |         await waitForPageToBeFullyLoaded(this.page);
  283 |     }
  284 |         
  285 |     
  286 |     /**
  287 |      * Enter a city in the search criteria
  288 |      * @param city - Name of the city to enter
  289 |      */
  290 |     async enterCity(city: string) {
  291 |         await this.cityCountyPostalInput.click();
  292 |         await this.cityCountyPostalInput.fill(city);
> 293 |         await this.page.click(`div.select2-result-label:has-text("${city}")`); //page.click('div.select2-result-label:has-text("${city}")');
      |                         ^ TimeoutError: page.click: Timeout 20000ms exceeded.
  294 |         //await waitForPageToBeFullyLoaded(this.page);
  295 |     }
  296 |     
  297 |     /**
  298 |      * Set minimum price in the search criteria
  299 |      * @param price - Minimum price value (without $ or commas)
  300 |      */
  301 |     async setMinimumPrice(price: string) {
  302 |         await this.minPriceDropdown.click();
  303 |         await this.minPriceInput.fill(price);
  304 |         await this.page.getByRole('option', { name: 'Min Price: $' }).click();
  305 |         //await waitForPageToBeFullyLoaded(this.page);
  306 |     }
  307 |     
  308 |     /**
  309 |      * Fill out the showcase widget form
  310 |      * @param widgetName - Name for the widget
  311 |      * @param width - Width of the widget in pixels (without 'px')
  312 |      * @param height - Height of the widget in pixels (without 'px')
  313 |      */
  314 |     async fillShowcaseWidgetForm(widgetName: string, width?: string, height?: string) {
  315 |         await this.widgetNameInput.click();
  316 |         await this.widgetNameInput.fill(widgetName);
  317 |         
  318 |         if (width) {
  319 |             await this.widthInput.click();
  320 |             await this.widthInput.fill(width);
  321 |         }
  322 |         
  323 |         if (height && this.heightInput) {
  324 |             await this.heightInput.click();
  325 |             await this.heightInput.fill(height);
  326 |         }
  327 |         
  328 |         await waitForPageToBeFullyLoaded(this.page);
  329 |     }
  330 |     
  331 |     /**
  332 |      * Build the widget (click the Build Widget button)
  333 |      */
  334 |     async buildWidget() {
  335 |         await this.buildWidgetButton.click();
  336 |         await waitForPageToBeFullyLoaded(this.page);
  337 |         
  338 |         // Wait for widget code to be visible
  339 |         await this.widgetCodeContainer.waitFor({ state: 'visible' });
  340 |     }
  341 |     
  342 |     /**
  343 |      * Preview the widget (opens in a new tab)
  344 |      * @returns The new page object for the preview window
  345 |      */
  346 |     async previewWidget() {
  347 |         const previewPagePromise = this.page.waitForEvent('popup');
  348 |         await this.previewWidgetButton.click();
  349 |         return await previewPagePromise;
  350 |     }
  351 |     
  352 |     /**
  353 |      * Navigate back to the widgets list
  354 |      */
  355 |     async backToWidgetsList() {
  356 |         await this.backToWidgetsListButton.click();
  357 |         //await waitForPageToBeFullyLoaded(this.page);
  358 |     }
  359 |     
  360 |     /**
  361 |      * Create a showcase widget with custom search (complete flow)
  362 |      * @param widgetName - Name for the widget
  363 |      * @param propertyTypes - Array of property types to select
  364 |      * @param city - City to filter by
  365 |      * @param minPrice - Minimum price to filter by
  366 |      */
  367 |     async createShowcaseWidgetWithCustomSearch(
  368 |         widgetName: string,
  369 |         propertyTypes: ('Residential' | 'Land' | 'Commercial Sale' | 'Multi Family')[],
  370 |         city?: string,
  371 |         minPrice?: string
  372 |     ) {
  373 |         // Select showcase widget type
  374 |         await this.selectWidgetType('showcase');
  375 |         
  376 |         // Select custom search property set
  377 |         await this.selectPropertySet('customSearch');
  378 |         
  379 |         // Select Advanced Search page
  380 |         await this.selectSearchPage('Advanced Search');
  381 |         
  382 |         // Select property types
  383 |         await this.selectPropertyTypes(propertyTypes);
  384 |         
  385 |         // Set status if needed
  386 |         await this.statusDropdown.click();
  387 |         await this.page.locator('.select2-results').getByRole('option', { name: 'Active' }).click();
  388 |         
  389 |         // Enter city if provided
  390 |         if (city) {
  391 |             await this.enterCity(city);
  392 |         }
  393 |         
```