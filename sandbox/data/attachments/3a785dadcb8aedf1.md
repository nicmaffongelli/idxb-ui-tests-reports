# Test info

- Name: Type of user: Client >> MW Menu: Account >> Sub-menu: Contacts >> Create Contact - User: Client-Elite-1-Existing
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/clients/account/contacts/contacts.spec.ts:16:21

# Error details

```
TimeoutError: locator.selectOption: Timeout 20000ms exceeded.
Call log:
  - waiting for getByLabel('Contact Type')
    - locator resolved to <select class="span4" id="contactDescription" name="contactDescription">…</select>
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

    at CreateEditContactPage.selectContactType (/opt/atlassian/pipelines/agent/build/tests/pages/client/account/contacts/CreateEditContactPage.ts:67:36)
    at CreateEditContactPage.fillFormWithDefaultValues (/opt/atlassian/pipelines/agent/build/tests/pages/client/account/contacts/CreateEditContactPage.ts:167:16)
    at /opt/atlassian/pipelines/agent/build/tests/specs/clients/account/contacts/contacts.spec.ts:22:56
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
   1 | import { Page, Locator, expect } from '@playwright/test';
   2 | import { BasePage } from '../../../BasePage';
   3 |
   4 | export class CreateEditContactPage extends BasePage {
   5 |   // Page elements as private properties
   6 |   private readonly contactTypeDropdown: Locator;
   7 |   private readonly primaryContactCheckbox: Locator;
   8 |   private readonly firstNameInput: Locator;
   9 |   private readonly lastNameInput: Locator;
   10 |   private readonly emailInput: Locator;
   11 |   private readonly additionalEmailInput: Locator;
   12 |   private readonly companyNameInput: Locator;
   13 |   private readonly addressInput: Locator;
   14 |   private readonly phoneInput: Locator;
   15 |   private readonly additionalPhoneInput: Locator;
   16 |   private readonly faxInput: Locator;
   17 |   private readonly additionalContactInput: Locator;
   18 |   private readonly contactDescriptionInput: Locator;
   19 |   private readonly saveChangesButton: Locator;
   20 |   private readonly successMessage: Locator;
   21 |
   22 |   /**
   23 |    * Constructor initializes all page elements
   24 |    * @param page Playwright page object
   25 |    */
   26 |   constructor(page: Page) {
   27 |     super(page);
   28 |     this.contactTypeDropdown = page.getByLabel('Contact Type');
   29 |     this.primaryContactCheckbox = page.getByRole('checkbox', { name: 'Primary Contact' });
   30 |     this.firstNameInput = page.getByRole('textbox', { name: 'First Name*' });
   31 |     this.lastNameInput = page.getByRole('textbox', { name: 'Last Name*' });
   32 |     this.emailInput = page.getByRole('textbox', { name: 'Email*' });
   33 |     this.additionalEmailInput = page.getByRole('textbox', { name: 'Additional Email' });
   34 |     this.companyNameInput = page.getByRole('textbox', { name: 'Company Name' });
   35 |     this.addressInput = page.getByRole('textbox', { name: 'Address' });
   36 |     this.phoneInput = page.getByRole('textbox', { name: 'Phone', exact: true });
   37 |     this.additionalPhoneInput = page.getByRole('textbox', { name: 'Additional Phone' });
   38 |     this.faxInput = page.getByRole('textbox', { name: 'Fax' });
   39 |     this.additionalContactInput = page.getByRole('textbox', { name: 'Additional Contact' });
   40 |     this.contactDescriptionInput = page.getByRole('textbox', { name: 'Contact Description' });
   41 |     this.saveChangesButton = page.getByRole('button', { name: 'Save Changes' });
   42 |     this.successMessage = page.locator('#jGrowl');
   43 |   }
   44 |
   45 |   /**
   46 |    * Navigate to the create contact page
   47 |    */
   48 |   async navigateToCreateContactPage(): Promise<void> {
   49 |     await this.page.getByRole('listitem').filter({ hasText: 'HomeDashboardTraffic' }).locator('div').first().click();
   50 |     await this.page.locator('span').filter({ hasText: /^Account$/ }).click();
   51 |     await this.page.getByRole('link', { name: 'Contacts' }).click();
   52 |     await this.page.getByRole('link', { name: 'Create Contact' }).click();
   53 |   }
   54 |
   55 |   /**
   56 |    * Go directly to the create lead page
   57 |    */
   58 |   async goto(){
   59 |     await this.page.goto(this.envConfig.MW_BASE_URL + '/mgmt/contacts/create');
   60 |   }
   61 |
   62 |   /**
   63 |    * Select a contact type from the dropdown
   64 |    * @param contactType Type of contact: 'billing', 'designer', or 'manager'
   65 |    */
   66 |   async selectContactType(contactType: 'billing' | 'designer' | 'manager'): Promise<void> {
>  67 |     await this.contactTypeDropdown.selectOption(contactType);
      |                                    ^ TimeoutError: locator.selectOption: Timeout 20000ms exceeded.
   68 |   }
   69 |
   70 |   /**
   71 |    * Set the primary contact checkbox
   72 |    * @param isPrimary Whether this is a primary contact
   73 |    */
   74 |   async setPrimaryContact(isPrimary: boolean): Promise<void> {
   75 |     if (isPrimary) {
   76 |       await this.primaryContactCheckbox.check();
   77 |     } else {
   78 |       await this.primaryContactCheckbox.uncheck();
   79 |     }
   80 |   }
   81 |
   82 |   /**
   83 |    * Fill in the contact's name
   84 |    * @param firstName Contact's first name
   85 |    * @param lastName Contact's last name
   86 |    */
   87 |   async fillName(firstName: string, lastName: string): Promise<void> {
   88 |     await this.firstNameInput.fill(firstName);
   89 |     await this.lastNameInput.fill(lastName);
   90 |   }
   91 |
   92 |   /**
   93 |    * Fill in the contact's email addresses
   94 |    * @param email Primary email address
   95 |    * @param additionalEmail Optional secondary email address
   96 |    */
   97 |   async fillEmail(email: string, additionalEmail?: string): Promise<void> {
   98 |     await this.emailInput.fill(email);
   99 |     if (additionalEmail) {
  100 |       await this.additionalEmailInput.fill(additionalEmail);
  101 |     }
  102 |   }
  103 |
  104 |   /**
  105 |    * Set the company name
  106 |    * @param companyName The company name
  107 |    */
  108 |   async setCompanyName(companyName: string): Promise<void> {
  109 |     await this.companyNameInput.fill(companyName);
  110 |   }
  111 |
  112 |   /**
  113 |    * Set the address
  114 |    * @param address The contact's address
  115 |    */
  116 |   async setAddress(address: string): Promise<void> {
  117 |     await this.addressInput.fill(address);
  118 |   }
  119 |
  120 |   /**
  121 |    * Fill in phone numbers
  122 |    * @param phone Primary phone number
  123 |    * @param additionalPhone Optional additional phone number
  124 |    * @param fax Optional fax number
  125 |    */
  126 |   async fillPhoneNumbers(phone: string, additionalPhone?: string, fax?: string): Promise<void> {
  127 |     await this.phoneInput.fill(phone);
  128 |     
  129 |     if (additionalPhone) {
  130 |       await this.additionalPhoneInput.fill(additionalPhone);
  131 |     }
  132 |     
  133 |     if (fax) {
  134 |       await this.faxInput.fill(fax);
  135 |     }
  136 |   }
  137 |
  138 |   /**
  139 |    * Set additional contact information
  140 |    * @param additionalContact Additional contact information
  141 |    * @param description Description of the additional contact
  142 |    */
  143 |   async setAdditionalContactInfo(additionalContact: string, description: string): Promise<void> {
  144 |     await this.additionalContactInput.fill(additionalContact);
  145 |     await this.contactDescriptionInput.fill(description);
  146 |   }
  147 |
  148 |   /**
  149 |    * Save the contact form changes
  150 |    */
  151 |   async saveContact(): Promise<void> {
  152 |     await this.saveChangesButton.click();
  153 |   }
  154 |
  155 |   /**
  156 |    * Verify message that the contact was saved successfully
  157 |    */
  158 |   async verifySuccessMessage(): Promise<void> {
  159 |     await expect(this.successMessage).toContainText('Contact has been created successfully.');
  160 |   }
  161 |
  162 |   /**
  163 |    * Fill the form with default values
  164 |    */
  165 |   async fillFormWithDefaultValues(): Promise<void> {
  166 |     // Set contact type (we'll use 'billing' as the final value from the recording)
  167 |     await this.selectContactType('billing');
```