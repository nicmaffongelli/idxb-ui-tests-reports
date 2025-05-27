# Test info

- Name: Type of user: Client >> MW Menu: Account >> Sub-menu: Upgrade - User: Client-Engage-New >> Client can Upgrade and Downgrade multi user level - User: Client-Engage-New
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/clients/account/upgrade/upgradeCenter.spec.ts:33:29

# Error details

```
TimeoutError: locator.selectOption: Timeout 20000ms exceeded.
Call log:
  - waiting for locator('#ml-newLevel')
    - locator resolved to <select id="ml-newLevel" name="newMultiuserLevel">…</select>
  - attempting select option action
    2 × waiting for element to be visible and enabled
      - did not find some options
    - retrying select option action
    - waiting 20ms
    2 × waiting for element to be visible and enabled
      - did not find some options
    - retrying select option action
      - waiting 100ms
    39 × waiting for element to be visible and enabled
       - did not find some options
     - retrying select option action
       - waiting 500ms

    at UpgradeCenterPage.changeMultiuserLevel (/opt/atlassian/pipelines/agent/build/tests/pages/client/account/upgrade/UpgradeCenterPage.ts:144:40)
    at /opt/atlassian/pipelines/agent/build/tests/specs/clients/account/upgrade/upgradeCenter.spec.ts:39:29
```

# Page snapshot

```yaml
- navigation:
  - link "IDX Broker":
    - /url: /mgmt/dashboard
    - img "IDX Broker"
  - list:
    - listitem:
      - text: Sandbox
      - strong: "Signed in as:"
      - text: QA (3894)
    - listitem:
      - img
- text: Notifications
- strong: You’re all caught up! Keep an eye out for new notifications. We’ll post them here.
- navigation:
  - list:
    - listitem: Home +
    - listitem: Leads +
    - listitem: Listings +
    - listitem: Messages +
    - listitem:
      - link "MLS":
        - /url: /mgmt/mls-membership
    - listitem: Design +
    - listitem: Account -
    - listitem: Support +
- listitem:
  - link "Page Help":
    - /url: "#"
- heading "Upgrade Center Upgrade your account" [level=1]
- list:
  - listitem:
    - link "Account Type":
      - /url: "#accountTypeUpgrade"
  - listitem:
    - link "Multi User":
      - /url: "#multiuserUpgrade"
- heading "Current Account Level" [level=2]
- paragraph
- heading "51-100 Agents Multi-User" [level=3]
- paragraph
- heading "Available Multi User Levels" [level=2]
- table:
  - rowgroup:
    - row "Agents Description":
      - cell "Agents"
      - cell "Description"
  - rowgroup:
    - 'row "Single User 1 Agent: Featured Listings for up to one agent. Ideal for single agent/broker."':
      - cell "Single User":
        - strong: Single User
      - 'cell "1 Agent: Featured Listings for up to one agent. Ideal for single agent/broker."':
        - paragraph:
          - strong: "1 Agent:"
          - text: Featured Listings for up to one agent. Ideal for single agent/broker.
    - 'row "Team Level 2 Agents: Featured Listings, Bio Pages & Contact Routing for up to two agents."':
      - cell "Team Level":
        - strong: Team Level
      - 'cell "2 Agents: Featured Listings, Bio Pages & Contact Routing for up to two agents."':
        - paragraph:
          - strong: "2 Agents:"
          - text: Featured Listings, Bio Pages & Contact Routing for up to two agents.
    - 'row "3 - 10 Agents 3 to 10 Agents: Featured Listings, Bio Pages & Contact Routing for up to ten agents. Ideal for a small brokerage, or a team within a large firm."':
      - cell "3 - 10 Agents":
        - strong: 3 - 10 Agents
      - 'cell "3 to 10 Agents: Featured Listings, Bio Pages & Contact Routing for up to ten agents. Ideal for a small brokerage, or a team within a large firm."':
        - paragraph:
          - strong: "3 to 10 Agents:"
          - text: Featured Listings, Bio Pages & Contact Routing for up to ten agents. Ideal for a small brokerage, or a team within a large firm.
    - 'row "11 - 50 Agents 11 to 50 Agents: Featured Listings, Bio Pages & Contact Routing for up to fifty agents. Ideal for large brokerages."':
      - cell "11 - 50 Agents":
        - strong: 11 - 50 Agents
      - 'cell "11 to 50 Agents: Featured Listings, Bio Pages & Contact Routing for up to fifty agents. Ideal for large brokerages."':
        - paragraph:
          - strong: "11 to 50 Agents:"
          - text: Featured Listings, Bio Pages & Contact Routing for up to fifty agents. Ideal for large brokerages.
    - 'row "51 - 100 Agents 51 - 100 Agents: Featured Listings, Bio Pages & Contact Routing for up to one hundred agents. Ideal for large brokerages."':
      - cell "51 - 100 Agents":
        - strong: 51 - 100 Agents
      - 'cell "51 - 100 Agents: Featured Listings, Bio Pages & Contact Routing for up to one hundred agents. Ideal for large brokerages."':
        - paragraph:
          - strong: "51 - 100 Agents:"
          - text: Featured Listings, Bio Pages & Contact Routing for up to one hundred agents. Ideal for large brokerages.
    - 'row "More than 100 Agents 101 Agents or more: Featured Listings, Bio Pages & Contact Routing for more than one hundred agents. Ideal for large brokerages."':
      - cell "More than 100 Agents":
        - strong: More than 100 Agents
      - 'cell "101 Agents or more: Featured Listings, Bio Pages & Contact Routing for more than one hundred agents. Ideal for large brokerages."':
        - paragraph:
          - strong: "101 Agents or more:"
          - text: Featured Listings, Bio Pages & Contact Routing for more than one hundred agents. Ideal for large brokerages.
- heading "Terms" [level=2]
- paragraph:
  - text: You authorize IDX, LLC to charge your credit card for any pro-rated charges, in addition to your standard monthly charge. This amount will be charged to your account immediately. Please review
  - link "IDX, LLC. Terms of Service.":
    - /url: http://www.idxbroker.com/terms
- heading "Change Account Level" [level=2]
- text: By clicking the submit button below, you are requesting an immediate account
- strong: upgrade
- text: to the level
- combobox:
  - option "Single User"
  - option "Team Level"
  - option "3 - 10 Agents"
  - option "11 - 50 Agents"
  - option "More than 100 Agents" [selected]
- text: with
- textbox: "1"
- text: additional blocks of 50 agents each. This will give your account a
- strong: "150"
- text: agent capacity and will
- strong: increase
- text: your monthly recurring charges by
- strong: $40.00
- text: to a recurring total of
- strong: $264.00
- text: . In addition, a prorated amount will be charged to the card on file to cover the remainder of the current billing period.
- checkbox
- text: Yes, I agree to the
- strong: increased
- text: monthly charges detailed above.
- button "Submit Now" [disabled]
- paragraph:
  - text: Services © 2025
  - link "IDX Broker":
    - /url: https://www.idxbroker.com
  - text: . All rights reserved.
```

# Test source

```ts
   44 |     this.accountTypeSubmitButton = page.locator('#accountTypeSubmit');
   45 |     
   46 |     // Multi-user section elements
   47 |     this.currentMultiuserLevel = page.locator('#multiuserUpgrade h3.alert');
   48 |     this.newMultiuserLevelSelect = page.locator('#ml-newLevel');
   49 |     this.newBlocksInput = page.locator('#newBlocks');
   50 |     this.multiuserAgreeCheckbox = page.locator('#multiuserAgree');
   51 |     this.multiuserSubmitButton = page.locator('#multiuserSubmit');
   52 |
   53 |     // Confirmation dialog elements
   54 |     this.confirmationTitle = page.locator('#detailModal .modal-header h3');
   55 |     this.confirmSoldDataRemovalButton = page.locator('#confirmSoldDataRemovalBtn');
   56 |     this.confirmRestrictedTemplateRemovalButton = page.locator('#restrictedTemplateRemovalButton');
   57 |     
   58 |     this.returnToUpgradeCenterLink = page.getByRole('link', { name: 'Return to the upgrade center' });
   59 |   }
   60 |
   61 |   /**
   62 |    * Navigate directly to the Upgrade Center page
   63 |    */
   64 |   async goto(): Promise<void> {
   65 |     await this.page.goto(this.envConfig.MW_BASE_URL + '/mgmt/upgrade');
   66 |   }
   67 |   
   68 |   /**
   69 |    * Get the current account type displayed on the page
   70 |    * @returns The current account type as a string
   71 |    */
   72 |   async getCurrentAccountType(): Promise<string> {
   73 |     return (await this.currentAccountType.textContent()) ?? '';
   74 |   }
   75 |   
   76 |   /**
   77 |    * Navigate to the Multi-user tab
   78 |    */
   79 |   async navigateToMultiuserTab(): Promise<void> {
   80 |     await this.multiuserTab.click();
   81 |     await expect(this.currentMultiuserLevel).toBeVisible();
   82 |   }
   83 |   
   84 |   /**
   85 |    * Get the current multi-user level displayed on the page
   86 |    * @returns The current multi-user level as a string
   87 |    */
   88 |   async getCurrentMultiuserLevel(): Promise<string> {
   89 |     await this.navigateToMultiuserTab();
   90 |     return (await this.currentMultiuserLevel.textContent()) ?? '';
   91 |   }
   92 |   
   93 |   /**
   94 |    * Change account type
   95 |    * @param accountTypeValue The value attribute of the account type to select (e.g., '25')
   96 |    */
   97 |   async changeAccountType(accountTypeValue: string): Promise<void> {
   98 |     // Navigate to Account Type tab if not already there
   99 |     await this.accountTypeTab.click();
  100 |     
  101 |     // Select the new account type by value
  102 |     await this.newAccountTypeSelect.selectOption(accountTypeValue);
  103 |     
  104 |     // Agree to the terms
  105 |     await this.accountTypeAgreeCheckbox.check();
  106 |     
  107 |     // Verify the submit button is enabled
  108 |     await expect(this.accountTypeSubmitButton).toBeEnabled();
  109 |   }
  110 |   
  111 |   /**
  112 |    * Submit account type change
  113 |    */
  114 |   async submitAccountTypeChange(): Promise<void> {
  115 |     await this.accountTypeSubmitButton.click();
  116 |
  117 |     // Handle confirmation dialog if it appears
  118 |     if (await this.confirmSoldDataRemovalButton.isVisible()) {
  119 |         await this.confirmSoldDataRemovalButton.click();
  120 |     }
  121 |
  122 |     if (await this.confirmRestrictedTemplateRemovalButton.isVisible()) {
  123 |       await this.confirmRestrictedTemplateRemovalButton.click();
  124 |     }
  125 |     
  126 |     // Wait for confirmation modal
  127 |     await expect(this.confirmationTitle).toHaveText('Submission successful');
  128 |
  129 |     await this.returnToUpgradeCenterLink.click();
  130 |
  131 |     await waitForPageToBeFullyLoaded(this.page);
  132 |   }
  133 |   
  134 |   /**
  135 |    * Change multi-user level
  136 |    * @param levelValue The value attribute of the multi-user level to select (e.g., '1-2', '3-10')
  137 |    * @param blocks Optional number of additional blocks (only for '101+' level)
  138 |    */
  139 |   async changeMultiuserLevel(levelValue: string, blocks?: number): Promise<void> {
  140 |     // Navigate to Multi-user tab
  141 |     await this.navigateToMultiuserTab();
  142 |     
  143 |     // Select the new multi-user level by value
> 144 |     await this.newMultiuserLevelSelect.selectOption(levelValue);
      |                                        ^ TimeoutError: locator.selectOption: Timeout 20000ms exceeded.
  145 |     
  146 |     // If blocks are specified and the level requires blocks input
  147 |     if (blocks && levelValue === '101+') {
  148 |       await this.newBlocksInput.fill(blocks.toString());
  149 |     }
  150 |     
  151 |     // Agree to the terms
  152 |     await this.multiuserAgreeCheckbox.check();
  153 |     
  154 |     // Verify the submit button is enabled
  155 |     await expect(this.multiuserSubmitButton).toBeEnabled();
  156 |   }
  157 |   
  158 |   /**
  159 |    * Submit multi-user level change
  160 |    */
  161 |   async submitMultiuserLevelChange(): Promise<void> {
  162 |     await this.multiuserSubmitButton.click();
  163 |     
  164 |     // Wait for confirmation modal
  165 |     await expect(this.confirmationTitle).toHaveText('Submission successful');
  166 |
  167 |     await waitForPageToBeFullyLoaded(this.page);
  168 |
  169 |     await this.returnToUpgradeCenterLink.click();
  170 |
  171 |     await waitForPageToBeFullyLoaded(this.page);
  172 |   }
  173 |   
  174 | }
```