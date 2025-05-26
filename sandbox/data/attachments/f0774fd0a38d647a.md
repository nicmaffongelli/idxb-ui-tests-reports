# Test info

- Name: Type of user: Client >> MW Menu: Design >> Sub-menu: Branding - Colors >> Client can modify and save branding colors. Branding colors are displayed as expected in FE search page - Client: Client-Engage-New
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/branding/brandingColors.spec.ts:20:21

# Error details

```
TimeoutError: locator.screenshot: Timeout 20000ms exceeded.
Call log:
  - waiting for getByRole('navigation')

    at /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/branding/brandingColors.spec.ts:35:133
```

# Page snapshot

```yaml
- text: "{\"message\":\"failure to get a peer from the ring-balancer\"}"
```

# Test source

```ts
   1 | import { expect } from '@playwright/test';
   2 | import { test } from '../../../../fixtures/usersFixture';
   3 | import { USER_GROUPS_CONFIG } from '../../../../fixtures/userGroupsConfig';
   4 | import { EnvConfig } from '../../../../../env/env';
   5 | import * as allure from "allure-js-commons";
   6 |
   7 | const envConfig = EnvConfig.get();
   8 |
   9 | const clientsGroup = USER_GROUPS_CONFIG['engageNew'];
  10 |
  11 | test.describe('Type of user: Client', () => {
  12 |
  13 |     for (const { name, storageState, domain } of clientsGroup) {
  14 |
  15 |         test.describe('MW Menu: Design', () => {
  16 |             test.describe('Sub-menu: Branding - Colors', () => {
  17 |                 
  18 |                 test.use({ storageState });
  19 |
  20 |                 test(`Client can modify and save branding colors. Branding colors are displayed as expected in FE search page - Client: ${name}`, async ({ client }) => {
  21 |                     await allure.epic("Type of user: Client");
  22 |                     await allure.feature("MW Menu: Design");
  23 |                     await allure.story("Sub-menu: Branding -> Colors");
  24 |                     
  25 |                     await client.brandingColorsPage.goto();
  26 |                     await client.brandingColorsPage.setPrimaryColor('#D6823D');
  27 |                     await client.brandingColorsPage.setPrimaryButtonColor('#24D69B');
  28 |                     await client.brandingColorsPage.setSecondaryColor('#D6823D');
  29 |                     await client.brandingColorsPage.setSecondaryButtonColor('#4A97B0');
  30 |                     await client.brandingColorsPage.saveChanges();
  31 |     
  32 |                     await client.frontEndAddressSearchPage.goto(domain);
  33 |                     
  34 |                     //Do not use screenshot()method for the whole page, disclaimertext can be different
> 35 |                     const screenshotNavigationButtonsBar = await (await client.frontEndAddressSearchPage.getNavigationButtonsBar()).screenshot();
     |                                                                                                                                     ^ TimeoutError: locator.screenshot: Timeout 20000ms exceeded.
  36 |
  37 |                     const baseLineScreenshotNavigationButtonsBarPath = `${envConfig.ENVIRONMENT}-navigation-bar.png`;
  38 |                     expect(screenshotNavigationButtonsBar).toMatchSnapshot(baseLineScreenshotNavigationButtonsBarPath); 
  39 |
  40 |                     const screenshotActionsButton = await (await client.frontEndAddressSearchPage.getActionsButtons()).screenshot();
  41 |
  42 |                     const baseLineActionsButtonPath = `${envConfig.ENVIRONMENT}-actions-buttons.png`;
  43 |                     expect(screenshotActionsButton).toMatchSnapshot(baseLineActionsButtonPath);
  44 |                                     
  45 |                 });     
  46 |             });
  47 |         });  
  48 |     }
  49 | });
  50 |
  51 |
```