# Test info

- Name: Type of user: Client >> MW Menu: Design >> Sub-menu: Website >> Sub-menu: Saved Links >> Create Saved Link - User: Client-Engage-1-Existing
- Location: /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/website/savedLinks.spec.ts:21:29

# Error details

```
TimeoutError: locator.click: Timeout 20000ms exceeded.
Call log:
  - waiting for locator('#select2-drop .select2-results li:has-text("Portland")').first()

    at AddSavedLinkPage.fillSearchCriteria (/opt/atlassian/pipelines/agent/build/tests/pages/client/design/website/AddSavedLinkPage.ts:145:111)
    at AddSavedLinkPage.fillSearchCriteriaWithDefaultValues (/opt/atlassian/pipelines/agent/build/tests/pages/client/design/website/AddSavedLinkPage.ts:189:9)
    at /opt/atlassian/pipelines/agent/build/tests/specs/clients/design/website/savedLinks.spec.ts:28:29
```

# Page snapshot

```yaml
- navigation:
  - link "IDX Broker":
    - /url: /mgmt/dashboard
    - img "IDX Broker"
  - list:
    - listitem:
      - text: Staging
      - strong: "Signed in as:"
      - text: Nic (3978)
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
    - listitem: Design -
    - listitem: Account +
    - listitem: Support +
- listitem:
  - link "Page Help":
    - /url: "#"
- heading "Add Saved Link" [level=1]
- link "View All":
  - /url: /mgmt/savedlinks.php
- heading "Pick a search page" [level=3]
- text: Available Search Pages
- combobox [disabled]
- button "Next Step" [disabled]
- img
- text: Loading... 1
- heading "Select your criteria" [level=3]
- text: Select Market Area
- link "DateTime Stamp Now":
  - /url: javascript:void(0)
- text: Select Market Area
- button "DateTime Stamp Now"
- combobox "Select Market Area":
  - option
  - option "DateTime Stamp Now" [selected]
  - option "Regional Multiple Listing Service"
- text: Property Type
- link "Residential":
  - /url: javascript:void(0)
- text: Property Type
- button "Residential"
- combobox "Property Type":
  - option
  - option "Residential" [selected]
  - option "Multi-Family"
  - option "Farm And Ranch"
  - option "Commercial"
  - option "Land"
- text: Property Sub Type
- list:
  - listitem:
    - text: Property Sub Type
    - textbox "Property Sub Type"
- listbox "Property Sub Type":
  - option
  - option "Condominium"
  - option "Manufactured Home"
  - option "Single Family"
  - option "Single Family w/ Acreage"
  - option "Single Family w/ Rental"
  - option "Townhouse"
- text: Status
- list:
  - listitem:
    - text: "Status: Active"
    - link "Remove item":
      - /url: "#"
      - text: ×
  - listitem:
    - text: Status
    - textbox "Status": Portland
- listbox "Status":
  - option
  - option "Active" [selected]
  - option "Back On Market"
  - option "Accepting Backups"
  - option "Pending with Contingency"
- text: City, County, Postal Code
- list:
  - listitem:
    - text: City, County, Postal Code
    - textbox "City, County, Postal Code": City, County or Postal Code
- listbox "City, County, Postal Code":
  - group:
    - option "Portland"
  - group:
    - option "Anderson"
    - option "Andrews"
    - option "Angelina"
    - option "Brazoria"
    - option "Brewster"
    - option "Burleson"
    - option "Burnet"
    - option "Castro"
    - option "Chambers"
    - option "Cherokee"
    - option "Crockett"
    - option "Dallas"
    - option "Dawson"
    - option "Deaf Smith"
    - option "Denton"
    - option "Duval"
    - option "Falls"
    - option "Foard"
    - option "Fort Bend"
    - option "Freestone"
    - option "Gaines"
    - option "Galveston"
    - option "Guadalupe"
    - option "Hamilton"
    - option "Hardeman"
    - option "Hardin"
    - option "Harris"
    - option "Hemphill"
    - option "Hopkins"
    - option "Houston"
    - option "Hutchinson"
    - option "Jasper"
    - option "Jeff Davis"
    - option "Jefferson"
    - option "Jones"
    - option "Kinney"
    - option "Lamar"
    - option "Lamb"
    - option "Leon"
    - option "Liberty"
    - option "Limestone"
    - option "Live Oak"
    - option "Lubbock"
    - option "Madison"
    - option "McMullen"
    - option "Montgomery"
    - option "Nacogdoches"
    - option "Newton"
    - option "Orange"
    - option "Panola"
    - option "Parmer"
    - option "Polk"
    - option "Pushmataha"
    - option "Robertson"
    - option "Rusk"
    - option "Sabine"
    - option "San Augustine"
    - option "San Jacinto"
    - option "Shelby"
    - option "Smith"
    - option "Terrell"
    - option "Terry"
    - option "Trinity"
    - option "Tyler"
    - option "Yoakum"
  - group:
    - option "15956"
    - option "74560"
    - option "74562"
    - option "75043"
    - option "75062"
    - option "75068"
    - option "75081"
    - option "75137"
    - option "75207"
    - option "75231"
    - option "75417"
    - option "75473"
    - option "75494"
    - option "75633"
    - option "75643"
    - option "75702"
    - option "75760"
    - option "75766"
    - option "75785"
    - option "75803"
    - option "75835"
    - option "75839"
    - option "75844"
    - option "75845"
    - option "75846"
    - option "75851"
    - option "75858"
    - option "75860"
    - option "75862"
    - option "75901"
    - option "75904"
    - option "75928"
    - option "75929"
    - option "75930"
    - option "75931"
    - option "75932"
    - option "75933"
    - option "75935"
    - option "75936"
    - option "75937"
    - option "75938"
    - option "75939"
    - option "75942"
    - option "75943"
    - option "75944"
    - option "75945"
    - option "75946"
    - option "75948"
    - option "75949"
    - option "75951"
    - option "75954"
    - option "75956"
    - option "75959"
    - option "75960"
    - option "75961"
    - option "75962"
    - option "75964"
    - option "75965"
    - option "75966"
    - option "75968"
    - option "75971"
    - option "75972"
    - option "75973"
    - option "75974"
    - option "75975"
    - option "75977"
    - option "75979"
    - option "75980"
    - option "76457"
    - option "76525"
    - option "76531"
    - option "76538"
    - option "76642"
    - option "76653"
    - option "76667"
    - option "76687"
    - option "76693"
    - option "76943"
    - option "77095"
    - option "77335"
    - option "77351"
    - option "77357"
    - option "77360"
    - option "77371"
    - option "77406"
    - option "77471"
    - option "77494"
    - option "77512"
    - option "77519"
    - option "77520"
    - option "77521"
    - option "77538"
    - option "77549"
    - option "77585"
    - option "77611"
    - option "77612"
    - option "77615"
    - option "77625"
    - option "77626"
    - option "77630"
    - option "77631"
    - option "77632"
    - option "77640"
    - option "77650"
    - option "77651"
    - option "77656"
    - option "77657"
    - option "77659"
    - option "77660"
    - option "77662"
    - option "77663"
    - option "77664"
    - option "77665"
    - option "77668"
    - option "77701"
    - option "77702"
    - option "77703"
    - option "77705"
    - option "77706"
    - option "77707"
    - option "77713"
    - option "77825"
    - option "77836"
    - option "77856"
    - option "77864"
    - option "77865"
    - option "77959"
    - option "78007"
    - option "78022"
    - option "78071"
    - option "78108"
    - option "78341"
    - option "78605"
    - option "78832"
    - option "78867"
    - option "79027"
    - option "79035"
    - option "79036"
    - option "79045"
    - option "79098"
    - option "79227"
    - option "79252"
    - option "79316"
    - option "79323"
    - option "79331"
    - option "79339"
    - option "79343"
    - option "79355"
    - option "79359"
    - option "79360"
    - option "79378"
    - option "79531"
    - option "79714"
    - option "79734"
    - option "79830"
    - option "79848"
    - option "95979"
- text: Min Price
- link "Min Price":
  - /url: javascript:void(0)
- text: Min Price
- button "Min Price"
- textbox "Min Price"
- text: Max Price
- link "Max Price":
  - /url: javascript:void(0)
- text: Max Price
- button "Max Price"
- textbox "Max Price"
- text: Bedrooms
- link "Bedrooms":
  - /url: javascript:void(0)
- text: Bedrooms
- button "Bedrooms"
- combobox "Bedrooms":
  - option [selected]
  - option "Any Number"
  - option "Studio"
  - option "1+"
  - option "2+"
  - option "3+"
  - option "4+"
  - option "5+"
  - option "6+"
  - option "7+"
  - option "8+"
  - option "9+"
  - option "10+"
- text: Bathrooms
- link "Bathrooms":
  - /url: javascript:void(0)
- text: Bathrooms
- button "Bathrooms"
- combobox "Bathrooms":
  - option [selected]
  - option "Any Number"
  - option "1+"
  - option "2+"
  - option "3+"
  - option "4+"
  - option "5+"
  - option "6+"
  - option "7+"
  - option "8+"
  - option "9+"
  - option "10+"
- text: SqFt
- link "SqFt":
  - /url: javascript:void(0)
- text: SqFt
- button "SqFt"
- textbox "SqFt"
- text: ac
- link "ac":
  - /url: javascript:void(0)
- text: ac
- button "ac"
- textbox "ac"
- text: Price Reduction
- link "Price Reduced":
  - /url: javascript:void(0)
- text: Price Reduction
- button "Price Reduced"
- combobox "Price Reduction":
  - option [selected]
  - option "In the last day"
  - option "In the last 3 days"
  - option "In the last 7 days"
  - option "In the last 2 weeks"
  - option "In the last month"
- text: Max Days Listed
- link "Max Days Listed":
  - /url: javascript:void(0)
- text: Max Days Listed
- button "Max Days Listed"
- textbox "Max Days Listed"
- text: Refinement
- list:
  - listitem:
    - text: Refinement
    - textbox "Refinement": Image, Virtual Tour, Virtual Open House, Open House, Featured
- listbox "Refinement":
  - option "Has Image"
  - option "Has Virtual Tour"
  - option "Has Open House"
  - option "Has Virtual Open House"
  - option "Featured Listings"
- text: Results per page
- link "Results per page":
  - /url: javascript:void(0)
- text: Results per page
- button "Results per page"
- combobox "Results per page":
  - option [selected]
  - option "5"
  - option "10"
  - option "25"
  - option "50"
  - option "100"
- text: Sort By
- link "Sort By":
  - /url: javascript:void(0)
- text: Sort By
- button "Sort By"
- combobox "Sort By":
  - option [selected]
  - option "Newest Listings"
  - option "Oldest Listings"
  - option "Least expensive to most"
  - option "Most expensive to least"
  - option "Bedrooms (Low to High)"
  - option "Bedrooms (High to Low)"
  - option "Bathrooms (Low to High)"
  - option "Bathrooms (High to Low)"
  - option "Square Feet (Low to High)"
  - option "Square Feet (High to Low)"
- button "Reset"
- button "View Results in New Window"
- text: Elementary School
- listbox "Elementary School":
  - option "AB McBay"
  - option "ANSBERRY ELEMENTARY"
  - option "Alamo"
  - option "Anderson Elementary"
  - option "BISD"
  - option "BISD / JISD"
  - option "BROOKELAND"
  - option "BUNA"
  - option "BUNA ELEM"
  - option "Beaumont"
  - option "Birkes Elementary"
  - option "Broaddus"
  - option "Broaddus ISD"
  - option "BroaddusISD"
  - option "Brookeland ISD"
  - option "Brownfield ISD"
  - option "Buna Elementary"
  - option "Buna ISD"
  - option "Burkeville"
  - option "Burkeville ISD"
  - option "CENTER"
  - option "CENTER ISD"
  - option "CISD"
  - option "Center I.S.D."
  - option "Center School District:"
  - option "Central Heights I.S.D."
  - option "Chester ISD"
  - option "Colmesneil ISD"
  - option "Colonial Heights"
  - option "Colonial Hts"
  - option "Corrigan ISD"
  - option "Coston/Herty"
  - option "Crockett"
  - option "Cushing"
  - option "Cushing ISD"
  - option "Deweyville"
  - option "Deweyville ISD"
  - option "Dirks-Anderson Elementary"
  - option "Douglass"
  - option "Douglass ISD"
  - option "EISD"
  - option "EVANT ISD"
  - option "EXCELSIOR & CENTER"
  - option "Evadale"
  - option "Evadale/Vidor"
  - option "Excelsior"
  - option "Excelsior ISD"
  - option "Few"
  - option "Friona"
  - option "GISD"
  - option "Galveston ISD"
  - option "Garrison"
  - option "Garrison ISD"
  - option "Gary ISD"
  - option "George West Elementary"
  - option "Grapeland"
  - option "Groesbeck"
  - option "Groesbeck ISD"
  - option "Groveton ISD"
  - option "HIS"
  - option "HISD"
  - option "HUNTINGTON"
  - option "Hamilton ISD"
  - option "Hemohill ISD"
  - option "Hemophill School Dist."
  - option "Hemphill"
  - option "Hemphill, School District"
  - option "Hemphill ISD"
  - option "Hemphill Schol District"
  - option "Hemphill School Dist."
  - option "Hemphill School District"
  - option "Hemphill School District."
  - option "Henderson"
  - option "Hudson"
  - option "JASPER ISD"
  - option "JISD"
  - option "JMH"
  - option "JOAQUIN"
  - option "JOAQUIN ISD"
  - option "Jasper"
  - option "Jasper Jr. High"
  - option "Joaquin I.S.D."
  - option "KCISD"
  - option "KIRBYVILLE ELEM."
  - option "KISD"
  - option "KOUNTZE"
  - option "Kirbyville"
  - option "Kirbyville CISD"
  - option "Kirbyville Elementary"
  - option "Kirbyville ISD"
  - option "Klondike"
  - option "Kountze ISD"
  - option "Lamesa North Elememtary"
  - option "Lamesa North Elementary"
  - option "Lamesa South Elementary"
  - option "Latexo"
  - option "Latexo ISD"
  - option "Latexo or Crockett"
  - option "Livingston ISD"
  - option "Martinsville"
  - option "McBay Elementary"
  - option "Mexia"
  - option "NEWTON"
  - option "NEWTON ELEM"
  - option "NISD"
  - option "Nacogdoches ISD"
  - option "Newton Elementary"
  - option "Newton ISD"
  - option "North Elementary"
  - option "North Elementary School"
  - option "Ozona"
  - option "Parnell"
  - option "Parnell Elementary"
  - option "Parnell Elementary School"
  - option "Pineland"
  - option "Pineland ISD"
  - option "Public serves 1,2,3,4,5"
  - option "Raguet"
  - option "Raguet Elem"
  - option "Raguet Elem."
  - option "Raguet Elementary"
  - option "SAISD"
  - option "SAN AUGUSTINE ISD"
  - option "SHELBYVILLE ISD"
  - option "SISD"
  - option "San Augistine District"
  - option "San Augustine"
  - option "San Augustine ISD."
  - option "Seminole Elementary"
  - option "Shelbyville"
  - option "Slocum"
  - option "South Elementary"
  - option "Spurger ISD"
  - option "Stanley C Stanley Element"
  - option "TENAHA ISD"
  - option "TIMPSON ISD"
  - option "Tenaha"
  - option "Thomas J Rusk, NAC"
  - option "Three Rivers Elementary"
  - option "Three Rivers ISD"
  - option "Tierra Blanca"
  - option "Timpson"
  - option "Timpson School dist."
  - option "Travis Elementary"
  - option "Vidor ISD"
  - option "Warren"
  - option "Warren ISD"
  - option "Wellman Union ISD"
  - option "West Central"
  - option "West Orange"
  - option "West Sabine"
  - option "West Sabine ISD"
  - option "Wiederstein"
  - option "Woodville"
  - option "Woodville ISD"
  - option "ZISD"
  - option "Zavalla"
  - option "Zavalla ISD"
  - option "ZavallaISD"
- text: Junior High
- listbox "Junior High":
  - option "Aragon Middle School"
  - option "BISD"
  - option "BISD / JISD"
  - option "BROOKELAND"
  - option "BUNA"
  - option "BUNA JH"
  - option "Beaumont"
  - option "Bfld Jr. High"
  - option "Bfld Jr High"
  - option "Bfld Middle School"
  - option "Broaddus"
  - option "Broaddus ISD"
  - option "BroaddusISD"
  - option "Brookeland ISD"
  - option "Brookeland Jr High"
  - option "Brookeland Junior High"
  - option "Brownfield ISD"
  - option "Brownfield Middle School"
  - option "Buna ISD"
  - option "Buna Junior High"
  - option "Burkeville"
  - option "Burkeville ISD"
  - option "CENTER"
  - option "CENTER ISD"
  - option "CISD"
  - option "Central Heights I.S.D."
  - option "Chester ISD"
  - option "Colmesneil ISD"
  - option "Corrigan ISD"
  - option "Crockett"
  - option "Cushing"
  - option "Cushing ISD"
  - option "Deweyville"
  - option "Dobie J. Frank"
  - option "Douglass"
  - option "Douglass ISD"
  - option "EISD"
  - option "EVANT ISD"
  - option "Evadale"
  - option "Evadale/Vidor"
  - option "Excelsior"
  - option "Excelsior ISD"
  - option "Fort Davis"
  - option "Fort Davis JR High"
  - option "Friona"
  - option "GISD"
  - option "Galveston ISD"
  - option "Garrison"
  - option "Garrison ISD"
  - option "Gary ISD"
  - option "Gentry"
  - option "George West Jr High"
  - option "Grapeland"
  - option "Groesbeck"
  - option "Groesbeck ISD"
  - option "Groveton ISD"
  - option "HIS"
  - option "HISD"
  - option "HJH"
  - option "HUNTINGTON"
  - option "Hamilton ISD"
  - option "Hemphill"
  - option "Hemphill ISD"
  - option "Hempphill ISD"
  - option "Henderson"
  - option "Henphill ISD"
  - option "Hudson"
  - option "JASPER ISD"
  - option "JISD"
  - option "JJHS"
  - 'option "JJHS`"'
  - option "JMH"
  - option "JOAQUIN"
  - option "JOAQUIN ISD"
  - option "Jasper"
  - option "Jasper Junior High"
  - option "Jasper Junior High School"
  - option "Jasper Middle School"
  - option "Joaquin I.S.D."
  - option "KCISD"
  - option "KIRBYVILLE JR HIGH"
  - option "KOUNTZE"
  - option "Kirbyville"
  - option "Kirbyville CISD"
  - option "Kirbyville ISD"
  - option "Klondike"
  - option "Kountze ISD"
  - option "Lamesa Middle School"
  - option "Latexo"
  - option "Latexo ISD"
  - option "Latexo or Crockett"
  - option "Livingston ISD"
  - option "Martinsville"
  - option "Mexia"
  - option "Mexia Jr. High"
  - option "Mexia Junior High"
  - option "Middle School"
  - option "Mike Moses"
  - option "Mike Moses Jr. High"
  - option "Mike Moses Jr High"
  - option "Mike Moses Jr High, NAC"
  - option "NEWTON"
  - option "NEWTON JH"
  - option "NISD"
  - option "Nacogdoches ISD"
  - option "Navarro/George Junior Hig"
  - option "Newton ISD"
  - option "Newton Junior High"
  - option "Ozona"
  - option "Pineland"
  - option "Pineland ISD"
  - option "Public serves 6,7,8"
  - option "SAISD"
  - option "SAN AUGUSTINE ISD"
  - option "SHELBYVILLE ISD"
  - option "SISD"
  - option "San Augustine"
  - option "Seminole Junior High"
  - option "Seven Lakes Junior High"
  - option "Shelbyville"
  - option "Slocum"
  - option "Spurger ISD"
  - option "TENAHA ISD"
  - option "TIMPSON ISD"
  - option "TRINITY INTERMEDIATE"
  - option "Tenaha"
  - option "Three Rivers ISD"
  - option "Three Rivers JR/SR High"
  - option "Three Rivers Jr/Senior"
  - option "Timpson"
  - option "Timpson School dist."
  - option "Vidor ISD"
  - option "WSISD"
  - option "Warren"
  - option "Warren ISD"
  - option "Wellman Union ISD"
  - option "West Orange"
  - option "West Sabine"
  - option "West Sabine ISD"
  - option "Woodville"
  - option "Woodville ISD"
  - option "ZISD"
  - option "Zavalla"
  - option "Zavalla ISD"
  - option "ZavallaISD"
- text: Senior High School
- listbox "Senior High School":
  - option "BISD"
  - option "BISD / JISD"
  - option "BROOKELAND"
  - option "BUNA"
  - option "BUNA HS"
  - option "Beaumont"
  - option "Bfld High"
  - option "Bfld High School"
  - option "Bfld Sr. High"
  - option "Broaddus"
  - option "Broaddus ISD"
  - option "Brookeland High School"
  - option "Brookeland ISD"
  - option "BrosddusISD"
  - option "Brownfield High"
  - option "Brownfield High School"
  - option "Brownfield I.S.D."
  - option "Brownfield ISD"
  - option "Buna High School"
  - option "Buna ISD"
  - option "Burkeviile"
  - option "Burkevile ISD"
  - option "Burkeville"
  - option "Burkeville ISD"
  - option "Byron Steele"
  - option "CENTER"
  - option "CENTER ISD"
  - option "CISD"
  - option "CenterISD"
  - option "Central Heights I.S.D."
  - option "Centre ISD"
  - option "Chester ISD"
  - option "Colmesneil ISD"
  - option "Corrigan ISD"
  - option "Crockett"
  - option "Cushing"
  - option "Cushing ISD"
  - option "Cypress Falls"
  - option "Deweyville"
  - option "Douglass"
  - option "Douglass ISD"
  - option "EISD"
  - option "EVANT ISD"
  - option "Evadale"
  - option "Evadale/Vidor"
  - option "Fort Davis"
  - option "Fort Davis SR High"
  - option "Friona"
  - option "GISD"
  - option "Galveston ISD"
  - option "Garrison"
  - option "Garrison ISD"
  - option "Gary ISD"
  - option "George West High"
  - option "Goose Creek Memorial"
  - option "Grapeland"
  - option "Groesbeck"
  - option "Groesbeck ISD"
  - option "Groveton ISD"
  - option "HHS"
  - option "HIS"
  - option "HISD"
  - option "HUNTINGTON"
  - option "Hamilton ISD"
  - option "Hemphill"
  - option "Hemphill ISD"
  - option "Henderson"
  - option "Hudson"
  - option "Huntington ISD"
  - option "JASPER ISD"
  - option "JISD"
  - option "JMH"
  - option "JOAQUIN"
  - option "JOAQUIN ISD"
  - option "Jasper"
  - option "Jasper High"
  - option "Jasper High School"
  - option "Joaquin I.S.D."
  - option "KCISD"
  - option "KIRBYVILLE HIGH"
  - option "KISD"
  - option "KOUNTZE"
  - option "Kirbyville"
  - option "Kirbyville CISD"
  - option "Kirbyville High School"
  - option "Kirbyville ISD"
  - option "Kirbyville Sr High"
  - option "Klondike"
  - option "Kountze ISD"
  - option "LUMBERTON ISD"
  - option "Lamesa High School"
  - option "Latexo"
  - option "Latexo ISD"
  - option "Latexo or Crockett"
  - option "Little Cypress-Mauricevil"
  - option "Livingston ISD"
  - option "Lufkin"
  - option "Martinsville"
  - option "Mexia"
  - option "Mexia High"
  - option "Mexia High School"
  - option "NEWTON"
  - option "NEWTON HS"
  - option "NISD"
  - option "Nacogdoches"
  - option "Nacogdoches H.S."
  - option "Nacogdoches HS"
  - option "Nacogdoches High"
  - option "Nacogdoches High School"
  - option "Nacogdoches ISD"
  - option "Newton High School"
  - option "Newton ISD"
  - option "Ozona"
  - option "Pineland"
  - option "Pineland ISD"
  - option "Public serves 9 thru 12"
  - option "SAISD"
  - option "SAN AUGUSTINE ISD"
  - option "SHELBYVILLE ISD"
  - option "SISD"
  - option "San Augustine"
  - option "San Augusting"
  - option "Seminole High"
  - option "Seven Lakes High School"
  - option "Shelbyville"
  - option "Slocum"
  - option "Spurger ISD"
  - option "TENAHA ISD"
  - option "TIMPSON ISD"
  - option "TRINITY HIGH SCHOOL"
  - option "Tenaha"
  - option "Terry High School"
  - option "Three Rivers ISD"
  - option "Three Rivers JR/SR High"
  - option "Three Rivers Jr/Senior"
  - option "Timpson"
  - option "Timpson School dist."
  - option "Vidor ISD"
  - option "WSISD"
  - option "Warren"
  - option "Warren ISD"
  - option "Wellman Union ISD"
  - option "West Orange"
  - option "West Sabine"
  - option "West Sabine ISD"
  - option "Woodville"
  - option "Woodville HS"
  - option "Woodville ISD"
  - option "ZISD"
  - option "Zavalla"
  - option "Zavalla ISD"
  - option "ZavallaISD"
- text: Misc Interior
- listbox "Misc Interior":
  - option "Bookcase"
  - option "Ceiling Fan"
  - option "Desk"
  - option "Hot Tub/Spa"
  - option "Intercom"
  - option "Pull Down Stairs"
  - option "Skylights"
  - option "Wet Bar"
  - option "Window Coverings"
- text: Remarks
- textbox "Remarks"
- text: Lot Description/Size
- listbox "Lot Description/Size":
  - option "1 to 3 Acres"
  - option "1/2 to 1 Acre"
  - option "3 to 5 Acres"
  - option "5 to 10 Acres"
  - option "10 to 20 Acres"
  - option "20 to 50 Acres"
  - option "Creek"
  - option "Lake Frontage Leased"
  - option "Lake Frontage Owned"
  - option "Less than 1/2 Acre"
  - option "More Than 50 Acres"
  - option "River Frontage"
- text: Exterior
- listbox "Exterior":
  - option "Brick"
  - option "Masonite"
  - option "Other/See Remarks"
  - option "Siding"
  - option "Stone"
  - option "Stucco"
  - option "Wood"
- text: Misc. Exterior
- listbox "Misc. Exterior":
  - option "BBQ-Grill"
  - option "Circular Drive"
  - option "Covered Patio"
  - option "Fenced"
  - option "Hot Tub/Spa"
  - option "Landscaped"
  - option "Patio"
  - option "Pool Above Ground"
  - option "Pool In Ground"
  - option "Pool Indoor"
  - option "RV Parking"
  - option "Sprinkler System"
  - option "Storage Shed"
  - option "Workshop"
- text: Fireplace
- textbox "Min Fireplace"
- text: to
- textbox "Max Fireplace"
- text: Garage Type
- listbox "Garage Type":
  - option "1 Attach"
  - option "1 Carport"
  - option "1 Detach"
  - option "2 Attach"
  - option "2 Carports"
  - option "2 Detach"
  - option "3 or More Attach"
  - option "Converted"
  - option "None"
- link "Next Step":
  - /url: "#bookmarkToStep3"
- text: "2"
- paragraph:
  - text: Services © 2025
  - link "IDX Broker":
    - /url: https://www.idxbroker.com
  - text: . All rights reserved.
- status
- status: Residential
- status
- status: No matches found
- status
- status
- status
- status
- status
- status
- status
- status
- status
- status
- status
- status
- list:
  - listitem: No matches found
```

# Test source

```ts
   45 |      */
   46 |     constructor(page: Page) {
   47 |         super(page);
   48 |         
   49 |         // Step 1 elements
   50 |         this.methodSelector = page.locator('#methodSelector');
   51 |         this.nextStepButton = page.getByRole('button', { name: 'Next Step' });
   52 |         this.savedLinkIndicator = page.locator('#savedLinkIndicator');
   53 |         
   54 |         // Step 2 elements
   55 |         this.searchContainer = page.locator('#middlewareSearch');
   56 |         this.residentialTab = page.getByRole('link', { name: 'Residential' });
   57 |         this.statusDropdown = page.getByRole('textbox', { name: 'Status' });
   58 |         this.propertySubTypeDropdown = page.getByRole('textbox', { name: 'Property Sub Type' });
   59 |         this.cityCountyZipInput = page.locator('#s2id_autogen4');
   60 |         this.minPriceLink = page.getByRole('link', { name: 'Min Price' });
   61 |         this.minPriceInput = page.getByRole('combobox', { name: 'Min Price' });
   62 |         this.maxPriceLink = page.getByRole('link', { name: 'Max Price' });
   63 |         this.maxPriceInput = page.getByRole('combobox', { name: 'Max Price' });
   64 |         this.bedroomsLink = page.getByRole('link', { name: 'Bedrooms' });
   65 |         this.bathroomsLink = page.getByRole('link', { name: 'Bathrooms' });
   66 |         this.sqftLink = page.getByRole('link', { name: 'SqFt' });
   67 |         this.sqftInput = page.getByRole('combobox', { name: 'SqFt' });
   68 |         this.nextStepLinkButton = page.getByRole('link', { name: 'Next Step' });
   69 |         
   70 |         // Step 3 elements
   71 |         this.pageTitleInput = page.getByRole('textbox', { name: 'Page Title*' });
   72 |         this.linkNameInput = page.locator('#linkName');
   73 |         this.descriptionMetaInput = page.getByRole('textbox', { name: 'Meta Tags Description' });
   74 |         this.keywordsInput = page.getByRole('textbox', { name: 'Meta Tags Keywords' });
   75 |         this.featuredYesRadio = page.locator('#featured-0');
   76 |         this.featuredNoRadio = page.locator('#featured-1');
   77 |         this.linkTitleInput = page.getByRole('textbox', { name: 'Link Display*' });
   78 |         this.linkCopyInput = page.getByRole('textbox', { name: 'Link Description' });
   79 |         this.saveAndCreateButton = page.getByRole('button', { name: 'Save & Create another link' });
   80 |         this.saveAndManageButton = page.getByRole('button', { name: 'Save & Manage links' });
   81 |     }
   82 |     
   83 |     /**
   84 |      * Navigate to Add Saved Link page through the menu
   85 |      */
   86 |     async navigateToAddSavedLink() {
   87 |         await this.page.locator('#idx-mw-navigation-bar').getByAltText('icon').click();
   88 |         await this.page.getByText('Design', { exact: true }).click();
   89 |         await this.page.getByText('Website', { exact: true }).click();
   90 |         await this.page.getByRole('link', { name: 'Saved Links' }).click();
   91 |         await this.page.getByRole('link', { name: 'Create Link' }).click();
   92 |     }
   93 |
   94 |     /**
   95 |      * Go directly to the creat elead page
   96 |      */
   97 |     async goto(){
   98 |         await this.page.goto(this.envConfig.MW_BASE_URL + '/mgmt/saved-links/create');
   99 |     }
  100 |     
  101 |     /**
  102 |      * Step 1: Select search page type and proceed to next step
  103 |      * @param searchPageType - The value of the search page to select
  104 |      */
  105 |     async selectSearchPageType(searchPageType: string) {
  106 |         await this.methodSelector.selectOption({ label: searchPageType });
  107 |         await this.nextStepButton.click();
  108 |     }
  109 |     
  110 |     /**
  111 |      * Step 2: Fill search criteria for residential properties
  112 |      * @param criteria - Search criteria options
  113 |      */
  114 |     async fillSearchCriteria(criteria: {
  115 |         city?: string;
  116 |         minPrice?: string;
  117 |         maxPrice?: string;
  118 |         bedrooms?: string;
  119 |         bathrooms?: string;
  120 |         sqft?: string;
  121 |         status?: string;
  122 |     }) {
  123 |
  124 |         //Temporary workaround to select Residential property type
  125 |         await waitForPageToBeFullyLoaded(this.page);
  126 |         await this.residentialTab.click();
  127 |         await this.page.locator(`#select2-drop .select2-results li:has-text("Land")`).click();
  128 |         await waitForPageToBeFullyLoaded(this.page);
  129 |         await this.page.getByRole('link', { name: 'Land' }).click();
  130 |         await this.page.locator(`#select2-drop .select2-results li:has-text("Residential")`).click();
  131 |         await waitForPageToBeFullyLoaded(this.page);
  132 |         
  133 |         // Set status if provided
  134 |         if (criteria.status) {
  135 |             await this.statusDropdown.click();
  136 |             // Find the status option in the dropdown
  137 |             await this.page.locator(`#select2-drop .select2-results li:has-text("${criteria.status}")`).click();
  138 |         }
  139 |         
  140 |         // Set city if provided
  141 |         if (criteria.city) {
  142 |             await this.cityCountyZipInput.click();
  143 |             await this.cityCountyZipInput.fill(criteria.city);
  144 |             // Wait for dropdown to appear and click the matching city
> 145 |             await this.page.locator(`#select2-drop .select2-results li:has-text("${criteria.city}")`).first().click();
      |                                                                                                               ^ TimeoutError: locator.click: Timeout 20000ms exceeded.
  146 |         }
  147 |         
  148 |         // Set min price if provided
  149 |         if (criteria.minPrice) {
  150 |             await this.minPriceLink.click();
  151 |             await this.minPriceInput.fill(criteria.minPrice);
  152 |             await this.page.getByRole('option', { name: 'Min Price: $' }).click();
  153 |         }
  154 |         
  155 |         // Set max price if provided
  156 |         if (criteria.maxPrice) {
  157 |             await this.maxPriceLink.click();
  158 |             await this.maxPriceInput.fill(criteria.maxPrice);
  159 |             await this.page.getByRole('option', { name: 'Max Price: $' }).click();
  160 |         }
  161 |         
  162 |         // Set bedrooms if provided
  163 |         if (criteria.bedrooms) {
  164 |             await this.bedroomsLink.click();
  165 |             await this.page.getByRole('option', { name: `Bedrooms: ${criteria.bedrooms}` }).click();
  166 |         }
  167 |         
  168 |         // Set bathrooms if provided
  169 |         if (criteria.bathrooms) {
  170 |             await this.bathroomsLink.click();
  171 |             await this.page.getByRole('option', { name: `Bathrooms: ${criteria.bathrooms}` }).click();
  172 |         }
  173 |         
  174 |         // Set sqft if provided
  175 |         if (criteria.sqft) {
  176 |             await this.sqftLink.click();
  177 |             await this.sqftInput.fill(criteria.sqft);
  178 |             await this.page.getByRole('option', { name: 'SqFt:' }).click();
  179 |         }
  180 |         
  181 |         // Move to next step
  182 |         await this.nextStepLinkButton.click();
  183 |     }
  184 |
  185 |     /**
  186 |      * Fill search criteria with default values
  187 |      */
  188 |     async fillSearchCriteriaWithDefaultValues(){
  189 |         await this.fillSearchCriteria({
  190 |             city: 'Portland',
  191 |             minPrice: '100000',
  192 |             maxPrice: '5000000',
  193 |             bedrooms: '1+',
  194 |             bathrooms: '1+',
  195 |             sqft: '100',
  196 |             status: 'Active',
  197 |         });
  198 |     }
  199 |     
  200 |     /**
  201 |      * Step 3: Fill in link settings and save
  202 |      * @param settings - Link settings options
  203 |      * @param saveAction - Whether to "create" another link or "manage" links
  204 |      */
  205 |     async fillLinkSettings(settings: {
  206 |         pageTitle: string;
  207 |         linkName?: string;
  208 |         description?: string;
  209 |         keywords?: string;
  210 |         featured?: boolean;
  211 |         linkTitle?: string;
  212 |         linkCopy?: string;
  213 |     }) {
  214 |         // Fill required fields
  215 |         await this.pageTitleInput.fill(settings.pageTitle);
  216 |         
  217 |         // Fill optional fields if provided
  218 |         if (settings.linkName) {
  219 |             await this.linkNameInput.fill(settings.linkName);
  220 |         }
  221 |         
  222 |         if (settings.description) {
  223 |             await this.descriptionMetaInput.fill(settings.description);
  224 |         }
  225 |         
  226 |         if (settings.keywords) {
  227 |             await this.keywordsInput.fill(settings.keywords);
  228 |         }
  229 |         
  230 |         if (settings.featured !== undefined) {
  231 |             if (settings.featured) {
  232 |                 await this.featuredYesRadio.check();
  233 |             } else {
  234 |                 await this.featuredNoRadio.check();
  235 |             }
  236 |         }
  237 |         
  238 |         if (settings.linkTitle) {
  239 |             await this.linkTitleInput.fill(settings.linkTitle);
  240 |         } else {
  241 |             // Use pageTitle as linkTitle if not provided
  242 |             await this.linkTitleInput.fill(settings.pageTitle);
  243 |         }
  244 |         
  245 |         if (settings.linkCopy) {
```