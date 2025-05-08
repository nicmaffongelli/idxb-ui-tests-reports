# Test info

- Name: Sign Up >> User Signup: Elite account type signup Completes Successfully
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/signUp/signUp.spec.ts:71:13

# Error details

```
TimeoutError: locator.pressSequentially: Timeout 20000ms exceeded.
Call log:
  - waiting for getByRole('textbox', { name: 'Card Number & Type*' })

    at SignUpPage3.fillPaymentForm (/opt/atlassian/pipelines/agent/build/tests/pages/common/SignUpPage3.ts:76:36)
    at SignUpPage3.fillPaymentFormWithDefaultValues (/opt/atlassian/pipelines/agent/build/tests/pages/common/SignUpPage3.ts:110:9)
    at /opt/atlassian/pipelines/agent/build/tests/specs/signUp/signUp.spec.ts:97:17
```

# Page snapshot

```yaml
- link "IDX Broker Logo":
  - /url: https://www.idxbroker.com
  - img "IDX Broker Logo"
- heading "IDX Broker Order Form Payment Information" [level=1]
- progressbar: Step 3 of 3
- text: Fields Marked * Are Required.
- heading "We're Sorry" [level=2]
- paragraph: A problem has occurred during the sign-up process. Please call (541) 343-3912 to complete your order.
- text: (541) 343-3912 IDX Data Services Provided by IDX, LLC Content ©2025 IDX, LLC, All Rights Reserved
```

# Test source

```ts
   1 | import { Page, Locator, expect } from '@playwright/test';
   2 | import { BasePage } from '../BasePage';
   3 | import { waitForPageToBeFullyLoaded } from '../../utils/page-utils';
   4 |
   5 | /**
   6 |  * Interface representing payment information data
   7 |  */
   8 | interface PaymentInfo {
   9 |     cardNumber: string;
   10 |     cvv: string;
   11 |     expirationMonth: string;
   12 |     expirationYear: string;
   13 |     nameOnCard: string;
   14 |     address1: string;
   15 |     address2?: string;
   16 |     city: string;
   17 |     state: string;
   18 |     zipCode: string;
   19 | }
   20 |
   21 | export class SignUpPage3 extends BasePage {
   22 |     // Card Information Elements
   23 |     private readonly cardNumberInput: Locator;
   24 |     private readonly cvvInput: Locator;
   25 |     private readonly expirationMonthSelect: Locator;
   26 |     private readonly expirationYearInput: Locator;
   27 |     private readonly nameOnCardInput: Locator;
   28 |     
   29 |     // Billing Address Elements
   30 |     private readonly address1Input: Locator;
   31 |     private readonly address2Input: Locator;
   32 |     private readonly cityInput: Locator;
   33 |     private readonly stateSelect: Locator;
   34 |     private readonly zipCodeInput: Locator;
   35 |     
   36 |     // Form Actions
   37 |     private readonly saveButton: Locator;
   38 |     
   39 |     // Card Icons for visual verification
   40 |     private readonly visaIcon: Locator;
   41 |     private readonly mastercardIcon: Locator;
   42 |     private readonly amexIcon: Locator;
   43 |     private readonly discoverIcon: Locator;
   44 |
   45 |     constructor(page: Page) {
   46 |         super(page);
   47 |
   48 |         // Initialize Card Information Locators
   49 |         this.cardNumberInput = page.getByRole('textbox', { name: 'Card Number & Type*' });
   50 |         this.cvvInput = page.getByRole('textbox', { name: 'CVV' });
   51 |         this.expirationMonthSelect = page.locator('#field_creditCardExpirationMonth');
   52 |         this.expirationYearInput = page.getByRole('textbox', { name: 'YYYY' });
   53 |         this.nameOnCardInput = page.getByRole('textbox', { name: 'Name on Card *' });
   54 |         
   55 |         // Initialize Billing Address Locators
   56 |         this.address1Input = page.getByRole('textbox', { name: 'Address*' });
   57 |         this.address2Input = page.getByRole('textbox', { name: 'Address2' });
   58 |         this.cityInput = page.getByRole('textbox', { name: 'City*' });
   59 |         this.stateSelect = page.getByLabel('State/Province and Postal');
   60 |         this.zipCodeInput = page.locator('#field_creditCardPostalCode');
   61 |         
   62 |         // Initialize Action Locators
   63 |         this.saveButton = page.getByRole('button', { name: 'Save changes' });
   64 |         
   65 |         // Initialize Card Icons Locators
   66 |         this.visaIcon = page.locator('#cardIcon-visa');
   67 |         this.mastercardIcon = page.locator('#cardIcon-mastercard');
   68 |         this.amexIcon = page.locator('#cardIcon-amex');
   69 |         this.discoverIcon = page.locator('#cardIcon-discover');
   70 |     }
   71 |
   72 |     async fillPaymentForm(paymentInfo: PaymentInfo) {
   73 |         await waitForPageToBeFullyLoaded(this.page);
   74 |         // Fill Card Information
   75 |         await this.page.waitForTimeout(1000);
>  76 |         await this.cardNumberInput.pressSequentially(paymentInfo.cardNumber, { delay: 100 });
      |                                    ^ TimeoutError: locator.pressSequentially: Timeout 20000ms exceeded.
   77 |         await this.page.keyboard.press('Tab');
   78 |         await this.page.waitForTimeout(1000);
   79 |         await this.cvvInput.pressSequentially(paymentInfo.cvv, { delay: 100 });
   80 |         await this.page.keyboard.press('Tab');
   81 |         await this.page.waitForTimeout(1000);
   82 |         await this.expirationYearInput.pressSequentially(paymentInfo.expirationYear, { delay: 100 });
   83 |         await this.page.keyboard.press('Tab');
   84 |         await this.page.waitForTimeout(1000);
   85 |         await this.nameOnCardInput.fill(paymentInfo.nameOnCard);
   86 |         
   87 |         // Fill Billing Address
   88 |         await this.address1Input.fill(paymentInfo.address1);
   89 |         /*
   90 |         if (paymentInfo.address2) {
   91 |             await this.address2Input.fill(paymentInfo.address2);
   92 |         }
   93 |         */
   94 |         await this.cityInput.fill(paymentInfo.city);
   95 |         await this.stateSelect.selectOption(paymentInfo.state);
   96 |         await this.zipCodeInput.fill(paymentInfo.zipCode);
   97 |     }
   98 |
   99 |     async fillPaymentFormWithDefaultValues(){
  100 |         let cvv = '';
  101 |         for (let i = 0; i < 3; i++) {
  102 |           cvv += Math.floor(Math.random() * 10).toString();
  103 |         }
  104 |         const randomCard = this.getRandomCreditCard();
  105 |         const currentYear = new Date().getFullYear();
  106 |         const month = (1 + Math.floor(Math.random() * 12)).toString().padStart(2, '0');
  107 |         const year = (currentYear + 1 + Math.floor(Math.random() * 5)).toString();
  108 |             
  109 |
  110 |         await this.fillPaymentForm({
  111 |             cardNumber: randomCard.number,
  112 |             cvv: cvv,
  113 |             expirationMonth: month,
  114 |             expirationYear: year,
  115 |             nameOnCard: 'Qa UiAutomation',
  116 |             address1: '3562 SE Harrison St',
  117 |             address2: '1B',
  118 |             city: 'Portland',
  119 |             state: 'OR',
  120 |             zipCode: '97214',
  121 |         });
  122 |     }
  123 |
  124 |     /**
  125 |      * Returns a random credit card from the test cards array
  126 |      */
  127 |     getRandomCreditCard() {
  128 |         const randomIndex = Math.floor(Math.random() * SignUpPage3.testCreditCards.length);
  129 |         return SignUpPage3.testCreditCards[randomIndex];
  130 |     }    
  131 |
  132 |     // Define card data as a static property
  133 |     private static readonly testCreditCards = [
  134 |         { number: '4111111111111111', type: 'Visa' },
  135 |         { number: '4000056655665556', type: 'Visa' },
  136 |         { number: '5555555555554444', type: 'Mastercard' },
  137 |         { number: '5105105105105100', type: 'Mastercard' },
  138 |         { number: '5200828282828210', type: 'Mastercard' },
  139 |         { number: '2223000048400011', type: 'Mastercard' }
  140 |     ];
  141 |         
  142 |
  143 |     async submitPayment() {
  144 |         await waitForPageToBeFullyLoaded(this.page);
  145 |         await this.page.waitForTimeout(1000); 
  146 |         await this.saveButton.click();
  147 |     }
  148 |
  149 |     async verifyFormElements() {
  150 |         await expect(this.cardNumberInput).toBeVisible();
  151 |         await expect(this.cvvInput).toBeVisible();
  152 |         await expect(this.expirationMonthSelect).toBeVisible();
  153 |         await expect(this.expirationYearInput).toBeVisible();
  154 |         await expect(this.nameOnCardInput).toBeVisible();
  155 |         await expect(this.address1Input).toBeVisible();
  156 |         await expect(this.cityInput).toBeVisible();
  157 |         await expect(this.stateSelect).toBeVisible();
  158 |         await expect(this.zipCodeInput).toBeVisible();
  159 |         await expect(this.saveButton).toBeEnabled();
  160 |     }
  161 |
  162 | }
  163 |
```