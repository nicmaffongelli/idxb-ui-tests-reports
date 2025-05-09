# Test info

- Name: Type of user: Client >> MW Menu: Design >> Sub-menu: Settings >> Sub-menu: Global >> Global Settings - Email - Change email subject, send preview and verify in Message Center - User: engage_new
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/settings/emailGlobalPreferences.spec.ts:13:21

# Error details

```
TimeoutError: locator.click: Timeout 20000ms exceeded.
Call log:
  - waiting for getByRole('link', { name: 'Email Settings' })

    at GlobalPreferencesPage.updateEmailSubject (/opt/atlassian/pipelines/agent/build/tests/pages/client/design/settings/GlobalPreferencesPage.ts:700:33)
    at /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/settings/emailGlobalPreferences.spec.ts:24:56
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
  600 |    * Save details tab settings and verify success message
  601 |    */
  602 |   async saveDetailsSettings(): Promise<void> {
  603 |     //await this.detailsTab.click();
  604 |     await this.detailsSaveButton.click();
  605 |     await this.verifySuccessMessage('Details Page Settings have been saved.');
  606 |   }
  607 |   
  608 |   /**
  609 |    * Save map tab settings and verify success message
  610 |    */
  611 |   async saveMapSettings(): Promise<void> {
  612 |     //await this.mapTab.click();
  613 |     await this.mapSaveButton.click();
  614 |     await this.verifySuccessMessage('Map Settings have been saved.');
  615 |   }
  616 |   
  617 |   /**
  618 |    * Save properties tab settings and verify success message
  619 |    */
  620 |   async savePropertiesSettings(): Promise<void> {
  621 |     //await this.propertiesTab.click();
  622 |     await this.propertiesSaveButton.click();
  623 |     await this.verifySuccessMessage('Properties Settings have been saved.');
  624 |   }
  625 |   
  626 |   /**
  627 |    * Save email settings tab settings and verify success message
  628 |    */
  629 |   async saveEmailSettings(): Promise<void> {
  630 |     await this.emailSettingsTab.click();
  631 |     await this.emailSettingsSaveButton.click();
  632 |     await this.verifySuccessMessage('Email Settings have been saved.');
  633 |   }
  634 |   
  635 |   /**
  636 |    * Save social tab settings and verify success message
  637 |    */
  638 |   async saveSocialSettings(): Promise<void> {
  639 |     await this.socialTab.click();
  640 |     await this.socialSaveButton.click();
  641 |     await this.verifySuccessMessage('Social Settings have been saved.');
  642 |   }
  643 |   
  644 |   /**
  645 |    * Save mobile tab settings and verify success message
  646 |    */
  647 |   async saveMobileSettings(): Promise<void> {
  648 |     await this.mobileTab.click();
  649 |     await this.mobileSaveButton.click();
  650 |     await this.verifySuccessMessage('Settings have been saved.');
  651 |   }
  652 |   
  653 |   /**
  654 |    * Save other tab settings and verify success message
  655 |    */
  656 |   async saveOtherSettings(): Promise<void> {
  657 |     await this.otherTab.click();
  658 |     await this.otherSaveButton.click();
  659 |     await this.verifySuccessMessage('Other Settings have been saved.');
  660 |   }
  661 |   
  662 |   /**
  663 |    * Save all tab settings sequentially
  664 |    */
  665 |   async saveAllSettings(): Promise<void> {
  666 |     await this.saveSearchSettings();
  667 |     await this.saveResultsSettings();
  668 |     await this.saveDetailsSettings();
  669 |     await this.saveMapSettings();
  670 |     await this.savePropertiesSettings();
  671 |     await this.saveEmailSettings();
  672 |     await this.saveSocialSettings();
  673 |     await this.saveMobileSettings();
  674 |     await this.saveOtherSettings();
  675 |   }
  676 |   
  677 |   /**
  678 |    * Set default price range and save search settings
  679 |    * @param minPrice The minimum price value to set
  680 |    * @param maxPrice The maximum price value to set
  681 |    */
  682 |   async setAndSaveDefaultPriceRange(minPrice: string | number, maxPrice: string | number): Promise<void> {
  683 |     await this.setDefaultPriceRange(minPrice, maxPrice);
  684 |     await this.saveSearchSettings();
  685 |   }
  686 |   
  687 |   /**
  688 |    * Verify success message after saving settings
  689 |    * @param expectedMessage The expected success message text
  690 |    */
  691 |   private async verifySuccessMessage(expectedMessage: string): Promise<void> {
  692 |     await expect(this.notificationMessage).toContainText(expectedMessage);
  693 |   }
  694 |
  695 |   /**
  696 |    * Update email subject line
  697 |    * @param subject The new subject line text
  698 |    */
  699 |   async updateEmailSubject(subject: string): Promise<void> {
> 700 |     await this.emailSettingsTab.click();
      |                                 ^ TimeoutError: locator.click: Timeout 20000ms exceeded.
  701 |     await this.subjectLineInput.fill(subject);
  702 |   }
  703 |
  704 |   /**
  705 |    * Send preview email and verify success
  706 |    */
  707 |   async sendPreviewEmail(): Promise<void> {
  708 |     await this.sendPreviewEmailButton.click();
  709 |     await this.verifySuccessMessage('Email Sent Successfully.');
  710 |   }
  711 |
  712 |   /**
  713 |    * Fill the preview sample email input
  714 |    * @param email Email address to use for preview
  715 |    */
  716 |   async fillPreviewSampleEmail(email: string): Promise<void> {
  717 |     await this.emailSettingsTab.click();
  718 |     await this.previewSampleEmailInput.fill(email);
  719 |   }
  720 | }
```