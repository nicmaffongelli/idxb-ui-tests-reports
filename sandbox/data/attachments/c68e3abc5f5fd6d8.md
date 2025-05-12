# Test info

- Name: Type of user: Client >> MW Menu: Account >> Sub-menu: Users >> Sub-menu: Agents >> Create Agent - User: Client-Elite-1-Existing
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/clients/account/users/agents.spec.ts:26:25

# Error details

```
TimeoutError: locator.fill: Timeout 20000ms exceeded.
Call log:
  - waiting for getByRole('textbox', { name: 'Email*' })

    at AddAgentPage.fillAccountContactInfo (/opt/atlassian/pipelines/agent/build/tests/pages/client/account/users/AddAgentPage.ts:114:31)
    at AddAgentPage.fillAccountContactInfoWithDefaultValuesAndEmail (/opt/atlassian/pipelines/agent/build/tests/pages/client/account/users/AddAgentPage.ts:150:20)
    at /opt/atlassian/pipelines/agent/build/tests/specs/clients/account/users/agents.spec.ts:32:51
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
- status
```

# Test source

```ts
   14 |     readonly lastNameField: Locator;
   15 |     readonly displayNameField: Locator;
   16 |     readonly titleField: Locator;
   17 |     readonly roleDropdown: Locator;
   18 |     readonly addressField: Locator;
   19 |     readonly cityField: Locator;
   20 |     readonly stateField: Locator;
   21 |     readonly zipField: Locator;
   22 |     readonly countryField: Locator;
   23 |     readonly homePhoneField: Locator;
   24 |     readonly homeFaxField: Locator;
   25 |     readonly cellPhoneField: Locator;
   26 |     readonly officePhoneField: Locator;
   27 |     readonly officeFaxField: Locator;
   28 |     readonly pagerField: Locator;
   29 |     readonly preferredPhoneDropdown: Locator;
   30 |     readonly smsOptInRadioYes: Locator;
   31 |     readonly smsOptInRadioNo: Locator;
   32 |     readonly smsAlertPhoneField: Locator;
   33 |     //readonly bioDetailsField: Locator;
   34 |     
   35 |     // Action buttons
   36 |     readonly saveChangesButton: Locator;
   37 |     readonly resetButton: Locator;
   38 |     
   39 |     // Success message
   40 |     readonly successMessage: Locator;
   41 |
   42 |     /**
   43 |      * Constructor - initializes the page object and locators
   44 |      * @param page - Playwright page object
   45 |      */
   46 |     constructor(page: Page) {
   47 |         super(page);
   48 |         
   49 |         // Initialize all locators
   50 |         this.emailField = page.getByRole('textbox', { name: 'Email*' });
   51 |         this.passwordField = page.getByRole('textbox', { name: 'Password*' });
   52 |         this.passwordToggle = page.locator('.toggle-password');
   53 |         this.firstNameField = page.getByRole('textbox', { name: 'First Name' });
   54 |         this.lastNameField = page.getByRole('textbox', { name: 'Last Name' });
   55 |         this.displayNameField = page.getByRole('textbox', { name: 'Display Name' });
   56 |         this.titleField = page.getByRole('textbox', { name: 'Title/Description' });
   57 |         this.roleDropdown = page.getByLabel('Role');
   58 |         this.addressField = page.getByRole('textbox', { name: 'Address' });
   59 |         this.cityField = page.getByRole('textbox', { name: 'City' });
   60 |         this.stateField = page.getByRole('textbox', { name: 'State/Province' });
   61 |         this.zipField = page.getByRole('textbox', { name: 'Zip Code' });
   62 |         this.countryField = page.getByRole('textbox', { name: 'Country' });
   63 |         this.homePhoneField = page.getByRole('textbox', { name: 'Home Phone' });
   64 |         this.homeFaxField = page.getByRole('textbox', { name: 'Home Fax' });
   65 |         this.cellPhoneField = page.getByRole('textbox', { name: 'Cell Phone' });
   66 |         this.officePhoneField = page.getByRole('textbox', { name: 'Office Phone' });
   67 |         this.officeFaxField = page.getByRole('textbox', { name: 'Office Fax' });
   68 |         this.pagerField = page.getByRole('textbox', { name: 'Pager' });
   69 |         this.preferredPhoneDropdown = page.getByLabel('Preferred Phone');
   70 |         this.smsOptInRadioYes = page.getByRole('radio', { name: 'Yes' });
   71 |         this.smsOptInRadioNo = page.getByRole('radio', { name: 'No' });
   72 |         this.smsAlertPhoneField = page.getByRole('textbox', { name: 'Phone', exact: true });
   73 |         
   74 |         // Actions
   75 |         this.saveChangesButton = page.getByRole('button', { name: 'Save Changes' });
   76 |         this.resetButton = page.getByRole('button', { name: 'Reset' });
   77 |         
   78 |         // Success message
   79 |         this.successMessage = page.locator('#jGrowl');
   80 |     }
   81 |
   82 |     /**
   83 |    * Go to directly to the Add Agent page
   84 |    */
   85 |   async goto(){
   86 |     await this.page.goto(envConfig.MW_BASE_URL + '/mgmt/agents/create');
   87 |   }
   88 |
   89 |     /**
   90 |      * Fill in the basic required account/contact information
   91 |      * @param agentInfo - Object containing agent information
   92 |      */
   93 |     async fillAccountContactInfo(agentInfo: {
   94 |         email: string,
   95 |         password: string,
   96 |         firstName: string,
   97 |         lastName: string,
   98 |         displayName: string,
   99 |         title: string,
  100 |         role: 'agent' | 'management' | 'staff',
  101 |         address?: string,
  102 |         city?: string,
  103 |         state?: string,
  104 |         zip?: string,
  105 |         country?: string,
  106 |         homePhone?: string,
  107 |         cellPhone?: string,
  108 |         officePhone?: string,
  109 |         preferredPhone?: 'agentCellPhone' | 'agentHomePhone' | 'agentOfficePhone',
  110 |         enableSmsAlerts?: boolean,
  111 |         smsAlertPhone?: string
  112 |     }) {
  113 |         // Fill required fields
> 114 |         await this.emailField.fill(agentInfo.email);
      |                               ^ TimeoutError: locator.fill: Timeout 20000ms exceeded.
  115 |         await this.passwordField.fill(agentInfo.password);
  116 |         await this.firstNameField.fill(agentInfo.firstName);
  117 |         await this.lastNameField.fill(agentInfo.lastName);
  118 |         await this.displayNameField.fill(agentInfo.displayName);
  119 |         await this.titleField.fill(agentInfo.title);
  120 |         await this.roleDropdown.selectOption(agentInfo.role);
  121 |
  122 |         // Fill optional fields if provided
  123 |         if (agentInfo.address) await this.addressField.fill(agentInfo.address);
  124 |         if (agentInfo.city) await this.cityField.fill(agentInfo.city);
  125 |         if (agentInfo.state) await this.stateField.fill(agentInfo.state);
  126 |         if (agentInfo.zip) await this.zipField.fill(agentInfo.zip);
  127 |         if (agentInfo.country) await this.countryField.fill(agentInfo.country);
  128 |         if (agentInfo.homePhone) await this.homePhoneField.fill(agentInfo.homePhone);
  129 |         if (agentInfo.cellPhone) await this.cellPhoneField.fill(agentInfo.cellPhone);
  130 |         if (agentInfo.officePhone) await this.officePhoneField.fill(agentInfo.officePhone);
  131 |         
  132 |         // Set preferred phone if provided
  133 |         if (agentInfo.preferredPhone) {
  134 |             await this.preferredPhoneDropdown.selectOption(agentInfo.preferredPhone);
  135 |         }
  136 |         
  137 |         // Configure SMS alerts if needed
  138 |         if (agentInfo.enableSmsAlerts) {
  139 |             await this.smsOptInRadioYes.check();
  140 |             if (agentInfo.smsAlertPhone) {
  141 |                 await this.smsAlertPhoneField.fill(agentInfo.smsAlertPhone);
  142 |             }
  143 |         }
  144 |     }
  145 |
  146 |     /**
  147 |      * Fill in the basic required account/contact information with default values
  148 |      */
  149 |     async fillAccountContactInfoWithDefaultValuesAndEmail(email: string) {
  150 |         await this.fillAccountContactInfo({
  151 |             email: email,
  152 |             password: '123456Asd!@#',
  153 |             firstName: 'Qa',
  154 |             lastName: 'UiAutomation',
  155 |             displayName: 'QaUiAutomation',
  156 |             title: 'DONT TOUCH',
  157 |             role: 'agent',
  158 |             address: '3562 SE Harrison St',
  159 |             city: 'Portland',
  160 |             state: 'Oregon',
  161 |             zip: '97214',
  162 |             country: 'United States',
  163 |             homePhone: '1001001002',
  164 |             cellPhone: '3055405076',
  165 |             officePhone: '1001001001',
  166 |             preferredPhone: 'agentCellPhone',
  167 |             enableSmsAlerts: true,
  168 |             smsAlertPhone: '+13055405076'
  169 |         });
  170 |     }
  171 |
  172 |     /**
  173 |      * Submit the form by clicking the Save Changes button
  174 |      */
  175 |     async saveChanges() {
  176 |         await this.saveChangesButton.click();
  177 |     }
  178 |
  179 |     /**
  180 |      * Reset the form by clicking the Reset button
  181 |      */
  182 |     async resetForm() {
  183 |         await this.resetButton.click();
  184 |     }
  185 |
  186 | }
```