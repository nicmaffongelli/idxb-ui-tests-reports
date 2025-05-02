# Test info

- Name: Authenticate SuperUser user and create a new client >> Authenticate SuperUser user and create a new client
- Location: /opt/atlassian/pipelines/agent/build/tests/setup/superUser.setup.ts:13:6

# Error details

```
Error: Timed out 20000ms waiting for expect(locator).toContainText(expected)

Locator: locator('#main-content')
Expected string: "Dashboard overview of your account"
Received: <element(s) not found>
Call log:
  - expect.toContainText with timeout 20000ms
  - waiting for locator('#main-content')
    - waiting for" https://elevate-qa.us.auth0.com/authorize/resume?state=W-hHctYzJjJebWEBT6X2JRnI5NNp7YFL" navigation to finish...
    - navigated to "https://elevate-qa.us.auth0.com/login?state=hKFo2SBQLVZIX2NsWnhhOXZKNE1Md2pWU2VsNEFYYlQ0M1Nqc6FupWxvZ2luo3RpZNkgWnZ2QV9ldE5RclJ4ZFVDRldvb1lUbzJfVjJzd3VPdzijY2lk2SBmYzI0S2FLRGpId1V0TEFyU3A4eFFrNmhaN2d…"

    at LoginPage.verifyLoginSuccess (/opt/atlassian/pipelines/agent/build/tests/pages/common/LoginPage.ts:34:54)
    at /opt/atlassian/pipelines/agent/build/tests/setup/superUser.setup.ts:23:5
```

# Page snapshot

```yaml
- main:
  - textbox "Email"
  - textbox "Password"
  - paragraph:
    - link "Don't remember your password?":
      - /url: https://middleware.idxsandbox.com/mgmt/password/recover
  - button "Log In"
```

# Test source

```ts
   1 | import { Page, Locator, expect } from '@playwright/test';
   2 | import { BasePage } from '../BasePage';
   3 | import { waitForPageToBeFullyLoaded } from '../../utils/page-utils';
   4 |
   5 | export class LoginPage extends BasePage {
   6 |   private emailInput: Locator;
   7 |   private passwordInput: Locator;
   8 |   private loginButton: Locator;
   9 |
  10 |   constructor(page: Page) {
  11 |     super(page);
  12 |     this.emailInput = page.getByRole('textbox', { name: 'Email' });
  13 |     this.passwordInput = page.getByRole('textbox', { name: 'Password' });
  14 |     this.loginButton = page.getByRole('button', { name: 'Log In' });
  15 |   }
  16 |
  17 |   async goto(): Promise<void> {
  18 |     const mw_dashboard_url = this.envConfig.MW_DASHBOARD_URL;
  19 |     if (!mw_dashboard_url) {
  20 |       throw new Error('URL_ENV_PART is not defined in the environment variables');
  21 |     }
  22 |     await this.page.goto(mw_dashboard_url);
  23 |   }
  24 |
  25 |   async login(email: string, password: string): Promise<void> {
  26 |     await this.emailInput.fill(email);
  27 |     await this.passwordInput.fill(password);
  28 |     await this.loginButton.click();
  29 |   }
  30 |
  31 |   async verifyLoginSuccess(): Promise<void> {
  32 |     await waitForPageToBeFullyLoaded(this.page);
  33 |     //Verify on the current page
> 34 |     await expect(this.page.locator('#main-content')).toContainText('Dashboard overview of your account');
     |                                                      ^ Error: Timed out 20000ms waiting for expect(locator).toContainText(expected)
  35 |   }
  36 | }
  37 |
```