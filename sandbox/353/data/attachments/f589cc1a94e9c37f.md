# Test info

- Name: User: Client-Engage-1-Existing >> Save Email Settings - User: Client-Engage-1-Existing
- Location: /opt/atlassian/pipelines/agent/build/src/tests/specs/clients/06_design/04_settings/01_global/globalPreferences.spec.ts:41:13

# Error details

```
TimeoutError: locator.click: Timeout 20000ms exceeded.
Call log:
  - waiting for getByRole('link', { name: 'Email Settings' })

    at EmailSettingsTabPage.navigateToEmailSettingsTab (/opt/atlassian/pipelines/agent/build/src/page-objects/client/06_design/04_settings/01_global/EmailSettingsTabPage.ts:30:33)
    at /opt/atlassian/pipelines/agent/build/src/tests/specs/clients/06_design/04_settings/01_global/globalPreferences.spec.ts:43:69
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
   1 | import { Page, Locator, expect, BasePage } from '@shared-client-imports';
   2 |
   3 | export class EmailSettingsTabPage extends BasePage {
   4 |   // Email Settings Elements
   5 |   private readonly subjectLineInput: Locator;
   6 |   private readonly sendPreviewEmailButton: Locator;
   7 |   private readonly previewSampleEmailInput: Locator;
   8 |   private readonly emailSettingsSaveButton: Locator;
   9 |   private readonly emailSettingsTab: Locator;
  10 |   private readonly notificationMessage: Locator;
  11 |   private readonly emailSettingsForm: Locator;
  12 |
  13 |   constructor(page: Page) {
  14 |     super(page);
  15 |
  16 |     // Initialize Email Settings Elements
  17 |     this.subjectLineInput = page.getByRole('textbox', { name: 'Subject Line' });
  18 |     this.sendPreviewEmailButton = page.getByRole('button', { name: 'Send Preview Email' });
  19 |     this.previewSampleEmailInput = page.getByRole('textbox', { name: 'Preview Sample Email' });
  20 |     this.emailSettingsSaveButton = page.locator('#emailSettings-form button.btn-primary');
  21 |     this.emailSettingsTab = page.getByRole('link', { name: 'Email Settings' });
  22 |     this.notificationMessage = page.locator('#jGrowl');
  23 |     this.emailSettingsForm = page.locator('#emailSettings-form');
  24 |   }
  25 |
  26 |   /**
  27 |    * Navigate to the Email Settings tab
  28 |    */
  29 |   async navigateToEmailSettingsTab(): Promise<void> {
> 30 |     await this.emailSettingsTab.click();
     |                                 ^ TimeoutError: locator.click: Timeout 20000ms exceeded.
  31 |     // Wait for the email settings form to be visible
  32 |     await this.emailSettingsForm.waitFor({ state: 'visible' });
  33 |   }
  34 |
  35 |   /**
  36 |    * Update email subject line
  37 |    * @param subject The new subject line text
  38 |    */
  39 |   async updateEmailSubject(subject: string): Promise<void> {
  40 |     await this.navigateToEmailSettingsTab();
  41 |     await this.subjectLineInput.fill(subject);
  42 |   }
  43 |
  44 |   /**
  45 |    * Send preview email and verify success
  46 |    */
  47 |   async sendPreviewEmail(): Promise<void> {
  48 |     await this.sendPreviewEmailButton.click();
  49 |     await this.verifySuccessMessage('Email Sent Successfully.');
  50 |   }
  51 |
  52 |   /**
  53 |    * Fill the preview sample email input
  54 |    * @param email Email address to use for preview
  55 |    */
  56 |   async fillPreviewSampleEmail(email: string): Promise<void> {
  57 |     await this.navigateToEmailSettingsTab();
  58 |     await this.previewSampleEmailInput.fill(email);
  59 |   }
  60 |
  61 |   /**
  62 |    * Save email settings tab settings and verify success message
  63 |    */
  64 |   async saveEmailSettings(): Promise<void> {
  65 |     await this.emailSettingsSaveButton.click();
  66 |     await this.verifySuccessMessage('Email Settings have been saved.');
  67 |   }
  68 |
  69 |   /**
  70 |    * Verify success message after saving settings
  71 |    * @param expectedMessage The expected success message text
  72 |    */
  73 |   private async verifySuccessMessage(expectedMessage: string): Promise<void> {
  74 |     await expect(this.notificationMessage).toContainText(expectedMessage);
  75 |   }
  76 | } 
```