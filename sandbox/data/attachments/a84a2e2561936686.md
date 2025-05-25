# Test info

- Name: Type of user: Client >> MW Menu: Design >> Sub-menu: Settings >> Sub-menu: Global >> Sub-menu: Results >> Client can perform a search in Basic Search FE page and the number of results is 25 - User: Client-Engage-1-Existing
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/settings/resultsGlobalPreferences.spec.ts:53:29

# Error details

```
TimeoutError: locator.click: Timeout 20000ms exceeded.
Call log:
  - waiting for locator('#IDX-formSubmit')

    at FrontEndBasicSearchPage.performSearch (/opt/atlassian/pipelines/agent/build/tests/pages/client/frontEndPages/FrontEndBasicSearchPage.ts:224:33)
    at /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/settings/resultsGlobalPreferences.spec.ts:59:66
```

# Page snapshot

```yaml
- text: "{\"message\":\"failure to get a peer from the ring-balancer\"}"
```

# Test source

```ts
  124 |     
  125 |     /**
  126 |      * Get the currently selected minimum price
  127 |      * @returns Promise resolving to the selected min price text or value
  128 |      */
  129 |     async getSelectedMinPrice(): Promise<string> {
  130 |         try {
  131 |             // First try to get the visible text in the Select2 dropdown
  132 |             return await this.selectedMinPrice.textContent() || '';
  133 |         } catch {
  134 |             // Fallback to getting the actual value from the select element
  135 |             return await this.minPriceDropdown.inputValue();
  136 |         }
  137 |     }
  138 |     
  139 |     /**
  140 |      * Get the currently selected maximum price
  141 |      * @returns Promise resolving to the selected max price text or value
  142 |      */
  143 |     async getSelectedMaxPrice(): Promise<string> {
  144 |         try {
  145 |             // First try to get the visible text in the Select2 dropdown
  146 |             return await this.selectedMaxPrice.textContent() || '';
  147 |         } catch {
  148 |             // Fallback to getting the actual value from the select element
  149 |             return await this.maxPriceDropdown.inputValue();
  150 |         }
  151 |     }
  152 |     
  153 |     /**
  154 |      * Get the numeric value of minimum price (removes currency symbols and formatting)
  155 |      * @returns Promise resolving to the numeric value of min price
  156 |      */
  157 |     async getMinPriceValue(): Promise<number> {
  158 |         const priceText = await this.getSelectedMinPrice();
  159 |         // Extract numeric value from price text (removes $, commas, etc)
  160 |         const numericValue = priceText.replace(/[^0-9]/g, '');
  161 |         return numericValue ? parseInt(numericValue, 10) : 0;
  162 |     }
  163 |     
  164 |     /**
  165 |      * Get the numeric value of maximum price (removes currency symbols and formatting)
  166 |      * @returns Promise resolving to the numeric value of max price
  167 |      */
  168 |     async getMaxPriceValue(): Promise<number> {
  169 |         const priceText = await this.getSelectedMaxPrice();
  170 |         // Extract numeric value from price text (removes $, commas, etc)
  171 |         const numericValue = priceText.replace(/[^0-9]/g, '');
  172 |         return numericValue ? parseInt(numericValue, 10) : 0;
  173 |     }
  174 |     
  175 |     /**
  176 |      * Verify the minimum price is set to the expected value
  177 |      * @param expectedPrice Expected price value (number or formatted string)
  178 |      */
  179 |     async verifyMinPrice(expectedPrice: string | number): Promise<void> {
  180 |         let expectedNumeric: number;
  181 |         
  182 |         if (typeof expectedPrice === 'string') {
  183 |             // If expected price is a string, convert to numeric
  184 |             expectedNumeric = parseInt(expectedPrice.replace(/[^0-9]/g, ''), 10);
  185 |         } else {
  186 |             expectedNumeric = expectedPrice;
  187 |         }
  188 |         
  189 |         const actualNumeric = await this.getMinPriceValue();
  190 |         expect(actualNumeric).toBe(expectedNumeric);
  191 |     }
  192 |     
  193 |     /**
  194 |      * Verify the maximum price is set to the expected value
  195 |      * @param expectedPrice Expected price value (number or formatted string)
  196 |      */
  197 |     async verifyMaxPrice(expectedPrice: string | number): Promise<void> {
  198 |         let expectedNumeric: number;
  199 |         
  200 |         if (typeof expectedPrice === 'string') {
  201 |             // If expected price is a string, convert to numeric
  202 |             expectedNumeric = parseInt(expectedPrice.replace(/[^0-9]/g, ''), 10);
  203 |         } else {
  204 |             expectedNumeric = expectedPrice;
  205 |         }
  206 |         
  207 |         const actualNumeric = await this.getMaxPriceValue();
  208 |         expect(actualNumeric).toBe(expectedNumeric);
  209 |     }
  210 |     
  211 |     /**
  212 |      * Select a property type
  213 |      * @param propertyType The property type to select
  214 |      */
  215 |     async selectPropertyType(propertyType: string): Promise<void> {
  216 |         await this.propertyTypeDropdown.click();
  217 |         await this.page.locator('.select2-results__option').getByText(propertyType, { exact: false }).click();
  218 |     }
  219 |      
  220 |     /**
  221 |      * Perform search with the current filter settings
  222 |      */
  223 |     async performSearch(): Promise<void> {
> 224 |         await this.searchButton.click();
      |                                 ^ TimeoutError: locator.click: Timeout 20000ms exceeded.
  225 |         await waitForPageToBeFullyLoaded(this.page);
  226 |     }
  227 |
  228 |     // --- CCZ Search Box Methods (Updated) ---
  229 |
  230 |     /**
  231 |      * Clicks the CCZ (City, County, Zip) search box to open it and waits for the input field.
  232 |      */
  233 |     async clickCczSearchBox(): Promise<void> {
  234 |         await this.cczSearchBox.click();
  235 |         // Wait for the dynamic input field to become visible (using default timeout)
  236 |         //await expect(this.cczInputField).toBeVisible();
  237 |     }
  238 |
  239 |     /**
  240 |      * Types text into the CCZ search box (dynamic input field) to filter suggestions.
  241 |      * Waits for the suggestion container to appear after typing.
  242 |      * @param searchText The text to type.
  243 |      */
  244 |     async typeInCczSearchBox(searchText: string): Promise<void> {
  245 |         // Use fill on the dynamic input field locator
  246 |         await this.cczInputField.pressSequentially(searchText, { delay: 100 });
  247 |         // Explicitly wait for the specific suggestions container ID to be visible after filling
  248 |         await expect(this.page.locator('#select2-IDX-ccz-select-results')).toBeVisible();
  249 |     }
  250 |
  251 |     /**
  252 |      * Verifies that a specific suggestion text exists in the CCZ dropdown results list.
  253 |      * Finds the list item containing the core text part (e.g., "Portland" from "Portland, OR").
  254 |      * @param suggestionText The full suggestion text (e.g., "Portland, OR" or "Shoshone, ID").
  255 |      */
  256 |     async verifyCczSuggestionExists(suggestionText: string): Promise<void> {
  257 |         // Extract the core part of the text (e.g., "Portland" from "Portland, OR", or just "Shoshone" if no comma)
  258 |         const coreText = suggestionText.split(',')[0].trim();
  259 |
  260 |         // Locate the specific list item (li with role="option") that contains the div with the exact label text
  261 |         const suggestionListItemLocator = this.page
  262 |             .locator('#select2-IDX-ccz-select-results li[role="option"].select2-results__option') // Target li[role="option"] within the specific container
  263 |             .filter({ has: this.page.locator(`div.IDX-custom-form-element__label:text-is("${coreText}")`) }); // Filter by the exact text in the label div
  264 |
  265 |         // Verify that this specific list item is visible
  266 |         await expect(suggestionListItemLocator).toBeVisible();
  267 |     }
  268 |
  269 |    /**
  270 |     * Verifies that a specific suggestion text is selected/present in the main CCZ group display area.
  271 |     * @param selectedText The exact text to verify (including potential prefixes like '×').
  272 |     */
  273 |     async verifyCczSelectedText(selectedText: string): Promise<void> {
  274 |         // Use default timeout
  275 |         await expect(this.cczGroup).toContainText(selectedText);
  276 |     }
  277 |
  278 |     // --- End CCZ Methods ---
  279 |
  280 |     // Snippet for FrontEndBasicSearchPage.ts
  281 |
  282 |     /**
  283 |      * Get the display name of the currently selected MLS
  284 |      * @returns Promise resolving to the display name of the selected MLS
  285 |      */
  286 |     async getSelectedMlsDisplayName(): Promise<string> {
  287 |         const container = this.page.locator('#select2-IDX-idxID-container');
  288 |         return await container.textContent() || '';
  289 |     }
  290 |
  291 |     /**
  292 |      * Verify the display name of the currently selected MLS
  293 |      * @param expectedDisplayName - The expected display name
  294 |      */
  295 |     async verifySelectedMlsDisplayName(expectedDisplayName: string): Promise<void> {
  296 |         // Directly assert on the container locator
  297 |         await expect(this.page.locator('#select2-IDX-idxID-container')).toContainText(expectedDisplayName);
  298 |     }
  299 |
  300 |     async verifyResultCount(expectedCount: number): Promise<void> {
  301 |         const resultCount = await this.listingCardImageOverlays.count();
  302 |         expect(resultCount).toEqual(expectedCount);
  303 |     }
  304 | }
```