# Test info

- Name: Type of user: Client >> MW Menu: Design >> Sub-menu: Settings >> Sub-menu: Global >> Set Map, Great Schools and Walk Score in Details Global Settings and verify in FE page - User: engage_new
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/settings/detailsGlobalPreferences.spec.ts:15:29

# Error details

```
TimeoutError: locator.dblclick: Timeout 20000ms exceeded.
Call log:
  - waiting for getByRole('link', { name: 'Details' })

    at GlobalPreferencesPage.navigateToDetailsTab (/opt/atlassian/pipelines/agent/build/tests/pages/client/design/settings/GlobalPreferencesPage.ts:221:27)
    at /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/settings/detailsGlobalPreferences.spec.ts:21:64
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
- status
```

# Test source

```ts
  121 |     this.displayMapRadioYes = page.locator('#displayMap-1');
  122 |     this.mapRefreshBehaviorSelect = page.locator('#mapRefreshBehavior');
  123 |     this.mapClusteringDesktopDisabled = page.locator('#mapClustering-0');
  124 |     this.mapClusteringDesktopEnabled = page.locator('#mapClustering-1');
  125 |     
  126 |     // Results tab elements
  127 |     this.resultsPerPageSelect = page.locator('#resultsPerPage');
  128 |     
  129 |     // Details tab elements
  130 |     this.mapTypeSelect = page.getByLabel('Map Type', { exact: true });
  131 |     this.displayGreatSchoolsRadioEnable = page.getByRole('radio', { name: 'Enable' });
  132 |     this.displayWalkscoreWidgetSelect = page.getByLabel('Display Walk Score Widget');
  133 |     
  134 |     // Your Properties tab elements - Featured Properties
  135 |     this.featuredThumbNo = page.locator('#featuredThumb-0');
  136 |     this.featuredThumbYes = page.locator('#featuredThumb-1');
  137 |     this.featuredRefinementSearchNo = page.locator('#featuredRefinementSearch-0');
  138 |     this.featuredRefinementSearchYes = page.locator('#featuredRefinementSearch-1');
  139 |     this.featuredShowSuppNo = page.locator('#featuredShowSupp-0');
  140 |     this.featuredShowSuppYes = page.locator('#featuredShowSupp-1');
  141 |     this.featuredPerPageSelect = page.locator('#featuredPerPage');
  142 |     this.featuredOrderBySelect = page.locator('#featuredOrderBy');
  143 |     this.featuredOHSortingSelect = page.locator('#featuredOHSorting');
  144 |     
  145 |     // Your Properties tab elements - Sold/Pending Properties
  146 |     this.soldPendingThumbNo = page.locator('#soldPendingThumb-0');
  147 |     this.soldPendingThumbYes = page.locator('#soldPendingThumb-1');
  148 |     this.soldPendingRefinementSearchNo = page.locator('#soldPendingRefinementSearch-0');
  149 |     this.soldPendingRefinementSearchYes = page.locator('#soldPendingRefinementSearch-1');
  150 |     this.soldPendingShowSuppNo = page.locator('#soldPendingShowSupp-0');
  151 |     this.soldPendingShowSuppYes = page.locator('#soldPendingShowSupp-1');
  152 |     this.soldPendingPerPageSelect = page.locator('#soldPendingPerPage');
  153 |     this.soldPendingOrderBySelect = page.locator('#soldPendingOrderBy');
  154 |     
  155 |     // Your Properties tab elements - Supplemental Properties
  156 |     this.suppThumbNo = page.locator('#suppThumb-0');
  157 |     this.suppThumbYes = page.locator('#suppThumb-1');
  158 |     this.suppRefinementSearchNo = page.locator('#suppRefinementSearch-0');
  159 |     this.suppRefinementSearchYes = page.locator('#suppRefinementSearch-1');
  160 |     this.suppPerPageSelect = page.locator('#suppPerPage');
  161 |     this.suppOrderBySelect = page.locator('#suppOrderBy');
  162 |
  163 |     // Initialize Email Settings Elements
  164 |     this.subjectLineInput = page.getByRole('textbox', { name: 'Subject Line' });
  165 |     this.sendPreviewEmailButton = page.getByRole('button', { name: 'Send Preview Email' });
  166 |     this.previewSampleEmailInput = page.getByRole('textbox', { name: 'Preview Sample Email' });
  167 |   }
  168 |
  169 |   /**
  170 |    * Navigate directly to the Global Preferences page
  171 |    */
  172 |   async goto(): Promise<void> {
  173 |     await this.page.goto(this.envConfig.MW_BASE_URL + '/mgmt/preferences');
  174 |   }
  175 |   
  176 |   /**
  177 |    * Navigate to the page via the navigation menu
  178 |    */
  179 |   async navigateFromMenu(): Promise<void> {
  180 |     // Click on the icon in the navbar
  181 |     await this.page.locator('#idx-mw-navigation-bar').getByAltText('icon').click();
  182 |     // Click on the Design menu item
  183 |     await this.page.getByText('Design', { exact: true }).click();
  184 |     // Click on the Settings submenu
  185 |     await this.page.getByText('Settings').click();
  186 |     // Click on the Global link
  187 |     await this.page.getByRole('link', { name: 'Global' }).click();
  188 |   }
  189 |   
  190 |   /**
  191 |    * Navigate to the Search tab
  192 |    */
  193 |   async navigateToSearchTab(): Promise<void> {
  194 |     await this.searchTab.click();
  195 |     // Wait for the search form to be visible
  196 |     await this.page.waitForSelector('#search-form', { state: 'visible' });
  197 |   }
  198 |   
  199 |   /**
  200 |    * Navigate to the Map tab
  201 |    */
  202 |   async navigateToMapTab(): Promise<void> {
  203 |     await this.mapTab.dblclick();
  204 |     // Wait for the map form to be visible
  205 |     await this.page.waitForSelector('#map-form', { state: 'visible' });
  206 |   }
  207 |   
  208 |   /**
  209 |    * Navigate to the Results tab
  210 |    */
  211 |   async navigateToResultsTab(): Promise<void> {
  212 |     await this.resultsTab.dblclick();
  213 |     // Wait for the results form to be visible
  214 |     await this.page.waitForSelector('#results-form', { state: 'visible' });
  215 |   }
  216 |   
  217 |   /**
  218 |    * Navigate to the Details tab
  219 |    */
  220 |   async navigateToDetailsTab(): Promise<void> {
> 221 |     await this.detailsTab.dblclick();
      |                           ^ TimeoutError: locator.dblclick: Timeout 20000ms exceeded.
  222 |     // Wait for the details form to be visible
  223 |     await this.page.waitForSelector('#details-form', { state: 'visible' });
  224 |   }
  225 |   
  226 |   /**
  227 |    * Navigate to the Properties tab
  228 |    */
  229 |   async navigateToPropertiesTab(): Promise<void> {
  230 |     await this.propertiesTab.dblclick();
  231 |     // Wait for the properties form to be visible
  232 |     await this.page.waitForSelector('#properties-form', { state: 'visible' });
  233 |   }
  234 |   
  235 |   /**
  236 |    * Set "All Results Page Maps" option to "No"
  237 |    */
  238 |   async setAllResultsPageMapsToNo(): Promise<void> {
  239 |     //await this.navigateToMapTab();
  240 |     await this.displayMapRadioNo.check();
  241 |   }
  242 |   
  243 |   /**
  244 |    * Set "All Results Page Maps" option to "Yes"
  245 |    */
  246 |   async setAllResultsPageMapsToYes(): Promise<void> {
  247 |     //await this.navigateToMapTab();
  248 |     await this.displayMapRadioYes.check();
  249 |   }
  250 |   
  251 |   /**
  252 |    * Set "Refresh Map" to "Manually" option
  253 |    */
  254 |   async setRefreshMapToManually(): Promise<void> {
  255 |     //await this.navigateToMapTab();
  256 |     await this.mapRefreshBehaviorSelect.selectOption('manual');
  257 |   }
  258 |   
  259 |   /**
  260 |    * Set "Refresh Map" to "Automatically" option
  261 |    */
  262 |   async setRefreshMapToAutomatically(): Promise<void> {
  263 |     //await this.navigateToMapTab();
  264 |     await this.mapRefreshBehaviorSelect.selectOption('auto');
  265 |   }
  266 |   
  267 |   /**
  268 |    * Enable Desktop Map Clustering
  269 |    */
  270 |   async enableDesktopMapClustering(): Promise<void> {
  271 |     //await this.navigateToMapTab();
  272 |     await this.mapClusteringDesktopEnabled.check();
  273 |   }
  274 |   
  275 |   /**
  276 |    * Disable Desktop Map Clustering
  277 |    */
  278 |   async disableDesktopMapClustering(): Promise<void> {
  279 |     //await this.navigateToMapTab();
  280 |     await this.mapClusteringDesktopDisabled.check();
  281 |   }
  282 |   
  283 |   /**
  284 |    * Get current Refresh Map behavior setting
  285 |    * @returns The current refresh map behavior value ('auto' or 'manual')
  286 |    */
  287 |   async getRefreshMapBehavior(): Promise<string> {
  288 |     //await this.navigateToMapTab();
  289 |     return await this.mapRefreshBehaviorSelect.inputValue();
  290 |   }
  291 |   
  292 |   /**
  293 |    * Check if Desktop Map Clustering is enabled
  294 |    * @returns True if enabled, false if disabled
  295 |    */
  296 |   async isDesktopMapClusteringEnabled(): Promise<boolean> {
  297 |     //await this.navigateToMapTab();
  298 |     return await this.mapClusteringDesktopEnabled.isChecked();
  299 |   }
  300 |   
  301 |   // Your Properties Tab - Featured Properties Methods
  302 |   
  303 |   /**
  304 |    * Toggle Featured Properties "Use Thumbnails If Available" setting
  305 |    */
  306 |   async toggleFeaturedThumbSetting(): Promise<void> {
  307 |     //await this.navigateToPropertiesTab();
  308 |     
  309 |     // Check which option is currently selected and select the other one
  310 |     if (await this.featuredThumbNo.isChecked()) {
  311 |       await this.featuredThumbYes.check();
  312 |     } else {
  313 |       await this.featuredThumbNo.check();
  314 |     }
  315 |   }
  316 |   
  317 |   /**
  318 |    * Toggle Featured Properties "Show Refinement Search" setting
  319 |    */
  320 |   async toggleFeaturedRefinementSearchSetting(): Promise<void> {
  321 |     //await this.navigateToPropertiesTab();
```