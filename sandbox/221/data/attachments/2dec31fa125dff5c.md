# Test info

- Name: Type of user: Client >> MW Menu: Design >> Sub-menu: Website >> Sub-menu: Saved Links >> Create Saved Link - User: Client-Elite-1-Existing
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
      - text: Sandbox
      - strong: "Signed in as:"
      - text: Nic (3266)
    - listitem:
      - text: "12"
      - img
- text: Notifications
- button "Clear All"
- text: retail clients only - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: all clients - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: retail clients only - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: all clients - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: retail clients only - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: all clients - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: retail clients only - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: all clients - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: retail clients only - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: all clients - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: retail clients only - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
- text: all clients - high
- button "Dismiss Notification":
  - img "Dismiss Notification"
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
- link "Regional Multiple Listing Service":
  - /url: javascript:void(0)
- text: Select Market Area
- button "Regional Multiple Listing Service"
- combobox "Select Market Area":
  - option
  - option "Texas MLS"
  - option "Regional Multiple Listing Service" [selected]
- text: Property Type
- link "Residential":
  - /url: javascript:void(0)
- text: Property Type
- button "Residential"
- combobox "Property Type":
  - option
  - option "Residential" [selected]
  - option "Commercial Sale"
  - option "Land"
  - option "Multi Family"
- text: Property Sub Type
- list:
  - listitem:
    - text: Property Sub Type
    - textbox "Property Sub Type"
- listbox "Property Sub Type":
  - option
  - option "Attached"
  - option "Co-op Housing"
  - option "Condominium"
  - option "Floating Home"
  - option "FloatingHome"
  - option "Manufactured Home in Park"
  - option "Manufactured Home on Real Property"
  - option "ManufacturedHomeinPark"
  - option "ManufacturedHomeonRealProperty"
  - option "Partially Owned"
  - option "PartiallyOwned"
  - option "Planned Community"
  - option "PlannedCommunity"
  - option "Single Family Residence"
  - option "SingleFamilyResidence"
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
  - option "Bumpable Buyer"
  - option "Pending"
  - option "Short Sale Pending"
  - option "Sold"
- text: City, County, Postal Code
- list:
  - listitem:
    - text: City, County, Postal Code
    - textbox "City, County, Postal Code": City, County or Postal Code
- listbox "City, County, Postal Code":
  - group:
    - option "Adams"
    - option "Albany"
    - option "Alsea"
    - option "Amboy"
    - option "Amity"
    - option "Anacortes"
    - option "Arch Cape"
    - option "Ariel"
    - option "Arlington"
    - option "Ashland"
    - option "Astoria"
    - option "Aumsville"
    - option "Aurora"
    - option "Azalea"
    - option "Baker City"
    - option "Bandon"
    - option "Banks"
    - option "Battle Ground"
    - option "Bay City"
    - option "Beatty"
    - option "Beavercreek"
    - option "Beaverton"
    - option "Bend"
    - option "Bickleton"
    - option "Bingen"
    - option "Birkenfeld"
    - option "Blachly"
    - option "Blue River"
    - option "Bly"
    - option "Boardman"
    - option "Boring"
    - option "Bremerton"
    - option "Brightwood"
    - option "Brookings"
    - option "Brownsville"
    - option "Brush Prairie"
    - option "Burns"
    - option "Camas"
    - option "Camas Valley"
    - option "Canby"
    - option "Cannon Beach"
    - option "Canyon City"
    - option "Canyonville"
    - option "Carlton"
    - option "Carson"
    - option "Castle Rock"
    - option "Cathlamet"
    - option "Cave Junction"
    - option "Centerville"
    - option "Central Point"
    - option "Centralia"
    - option "Chehalis"
    - option "Chemult"
    - option "Chiloquin"
    - option "Chinook"
    - option "Christmas Valley"
    - option "Clackamas"
    - option "Clatskanie"
    - option "Cloverdale"
    - option "Colton"
    - option "Columbia City"
    - option "Condon"
    - option "Coos Bay"
    - option "Coquille"
    - option "Corbett"
    - option "Cornelius"
    - option "Corvallis"
    - option "Cottage Grove"
    - option "Cougar"
    - option "Crabtree"
    - option "Crescent"
    - option "Crescent Lake"
    - option "Creswell"
    - option "Culver"
    - option "Dairy"
    - option "Dale"
    - option "Dallas"
    - option "Damascus"
    - option "Dayton"
    - option "Dayton"
    - option "Depoe Bay"
    - option "Detroit"
    - option "Dexter"
    - option "Donald"
    - option "Dorena"
    - option "Drain"
    - option "Dufur"
    - option "Dundee"
    - option "Durham"
    - option "Eagle Creek"
    - option "Eagle Point"
    - option "Elgin"
    - option "Elkton"
    - option "Elmira"
    - option "Enterprise"
    - option "Estacada"
    - option "Eugene"
    - option "Fairview"
    - option "Florence"
    - option "Forest Grove"
    - option "Fort Rock"
    - option "Fossil"
    - option "Foster"
    - option "Gales Creek"
    - option "Gardiner"
    - option "Garibaldi"
    - option "Gaston"
    - option "Gates"
    - option "Gearhart"
    - option "Gervais"
    - option "Gladstone"
    - option "Glendale"
    - option "Gleneden"
    - option "Gleneden Beach"
    - option "Glenwood"
    - option "Glide"
    - option "Gold Beach"
    - option "Goldendale"
    - option "Government Camp"
    - option "Grand Ronde"
    - option "Granite"
    - option "Grants Pass"
    - option "Grass Valley"
    - option "Greenhorn"
    - option "Gresham"
    - option "Haines"
    - option "Halfway"
    - option "Halsey"
    - option "Happy Valley"
    - option "Harrisburg"
    - option "Hebo"
    - option "Helix"
    - option "Heppner"
    - option "Hermiston"
    - option "Hillsboro"
    - option "Hines"
    - option "Hood River"
    - option "Hoquiam"
    - option "Hubbard"
    - option "Husum"
    - option "Idanha"
    - option "Ilwaco"
    - option "Imnaha"
    - option "Independence"
    - option "Ione"
    - option "Irrigon"
    - option "Island City"
    - option "Jacksonville"
    - option "Jefferson"
    - option "John Day"
    - option "Joseph"
    - option "Junction City"
    - option "Kalama"
    - option "Keizer"
    - option "Kelso"
    - option "Kimberly"
    - option "King City"
    - option "Kingston"
    - option "Klamath Falls"
    - option "Klickitat"
    - option "La Center"
    - option "La Grande"
    - option "La Pine"
    - option "Lafayette"
    - option "Lake Oswego"
    - option "Lakeside"
    - option "Langlois"
    - option "Lebanon"
    - option "Lincoln Beach"
    - option "Lincoln City"
    - option "Logsden"
    - option "Long Beach"
    - option "Long Creek"
    - option "Longview"
    - option "Lorane"
    - option "Lostine"
    - option "Lowell"
    - option "Lyle"
    - option "Lyons"
    - option "Madras"
    - option "Manning"
    - option "Manzanita"
    - option "Mapleton"
    - option "Marcola"
    - option "Maupin"
    - option "McKenzie Bridge"
    - option "McMinnville"
    - option "Meacham"
    - option "Medford"
    - option "Merlin"
    - option "Mill Creek"
    - option "Milton-Freewater"
    - option "Milwaukie"
    - option "Molalla"
    - option "Monmouth"
    - option "Monroe"
    - option "Moro"
    - option "Mosier"
    - option "Mossyrock"
    - option "Mount Angel"
    - option "Mount Vernon"
    - option "Mt Hood Prkdl"
    - option "Mulino"
    - option "Myrtle Creek"
    - option "Myrtle Point"
    - option "Napavine"
    - option "Nehalem"
    - option "Neotsu"
    - option "Neskowin"
    - option "Netarts"
    - option "Newberg"
    - option "Newport"
    - option "North Bend"
    - option "North Bonneville"
    - option "North Plains"
    - option "North Powder"
    - option "Noti"
    - option "Oakland"
    - option "Oakridge"
    - option "Ocean Park"
    - option "Oceanside"
    - option "Ontario"
    - option "Oregon City"
    - option "Otis"
    - option "Otter Rock"
    - option "Oxbow"
    - option "Pacific City"
    - option "Paisley"
    - option "Pe Ell"
    - option "Pendleton"
    - option "Philomath"
    - option "Pleasant Hill"
    - option "Plush"
    - option "Port Orford"
    - option "Portland"
    - option "Powell Butte"
    - option "Powers"
    - option "Prairie City"
    - option "Prineville"
    - option "Rainier"
    - option "Redmond"
    - option "Reedsport"
    - option "Rhododendron"
    - option "Rickreall"
    - option "Riddle"
    - option "Ridgefield"
    - option "Ritter"
    - option "Rockaway Beach"
    - option "Rogue River"
    - option "Roseburg"
    - option "Rufus"
    - option "Ryderwood"
    - option "Saint Helens"
    - option "Salem"
    - option "Salkum"
    - option "Sandy"
    - option "Scappoose"
    - option "Scio"
    - option "Seal Rock"
    - option "Seaside"
    - option "Seaview"
    - option "Sheridan"
    - option "Sherwood"
    - option "Silver Lake"
    - option "Silver Lake"
    - option "Silverton"
    - option "Sisters"
    - option "Skamania"
    - option "South Beach"
    - option "Sprague River"
    - option "Springfield"
    - option "Stanfield"
    - option "Stayton"
    - option "Stevenson"
    - option "Sumpter"
    - option "Sunriver"
    - option "Sutherlin"
    - option "Sweet Home"
    - option "Talent"
    - option "Tenmile"
    - option "The Dalles"
    - option "Tigard"
    - option "Tillamook"
    - option "Tiller"
    - option "Toledo"
    - option "Toledo"
    - option "Trail"
    - option "Trout Lake"
    - option "Troutdale"
    - option "Tualatin"
    - option "Turner"
    - option "Tygh Valley"
    - option "Ukiah"
    - option "Umatilla"
    - option "Umpqua"
    - option "Underwood"
    - option "Unknown"
    - option "Vader"
    - option "Vancouver"
    - option "Vashon"
    - option "Veneta"
    - option "Vernonia"
    - option "Vida"
    - option "Wahkiacus"
    - option "Waldport"
    - option "Wallowa"
    - option "Wallowa Lake"
    - option "Walton"
    - option "Wamic"
    - option "Warren"
    - option "Warrenton"
    - option "Wasco"
    - option "Washougal"
    - option "Welches"
    - option "West Linn"
    - option "Westfir"
    - option "Westlake"
    - option "Weston"
    - option "Westport"
    - option "Wheeler"
    - option "White City"
    - option "White Salmon"
    - option "Willamina"
    - option "Wilsonville"
    - option "Winchester"
    - option "Winchester Bay"
    - option "Winlock"
    - option "Winston"
    - option "Wishram"
    - option "Wolf Creek"
    - option "Wood Village"
    - option "Woodburn"
    - option "Woodland"
    - option "Yachats"
    - option "Yacolt"
    - option "Yamhill"
    - option "Yoncalla"
  - group:
    - option "Baker"
    - option "Benton"
    - option "Clackamas"
    - option "Clark"
    - option "Clatsop"
    - option "Columbia"
    - option "Columbia"
    - option "Coos"
    - option "Cowlitz"
    - option "Crook"
    - option "Curry"
    - option "Deschutes"
    - option "Douglas"
    - option "Gilliam"
    - option "Grant"
    - option "Grays Harbor"
    - option "Harney"
    - option "Hood River"
    - option "Jackson"
    - option "Jefferson"
    - option "Josephine"
    - option "King"
    - option "Kitsap"
    - option "Klamath"
    - option "Klickitat"
    - option "Lake"
    - option "Lane"
    - option "Lewis"
    - option "Lincoln"
    - option "Linn"
    - option "Malheur"
    - option "Marion"
    - option "Morrow"
    - option "Multnomah"
    - option "Pacific"
    - option "Polk"
    - option "Sherman"
    - option "Skagit"
    - option "Skamania"
    - option "Snohomish"
    - option "Tillamook"
    - option "Umatilla"
    - option "Union"
    - option "Wahkiakum"
    - option "Wallowa"
    - option "Wasco"
    - option "Washington"
    - option "Wheeler"
    - option "Yamhill"
  - group:
    - option "97002"
    - option "97003"
    - option "97004"
    - option "97005"
    - option "97006"
    - option "97007"
    - option "97008"
    - option "97009"
    - option "97011"
    - option "97013"
    - option "97015"
    - option "97016"
    - option "97017"
    - option "97018"
    - option "97019"
    - option "97020"
    - option "97021"
    - option "97022"
    - option "97023"
    - option "97024"
    - option "97026"
    - option "97027"
    - option "97028"
    - option "97029"
    - option "97030"
    - option "97031"
    - option "97032"
    - option "97034"
    - option "97035"
    - option "97037"
    - option "97038"
    - option "97039"
    - option "97040"
    - option "97041"
    - option "97042"
    - option "97045"
    - option "97048"
    - option "97049"
    - option "97050"
    - option "97051"
    - option "97053"
    - option "97055"
    - option "97056"
    - option "97058"
    - option "97060"
    - option "97062"
    - option "97063"
    - option "97064"
    - option "97065"
    - option "97067"
    - option "97068"
    - option "97070"
    - option "97071"
    - option "97078"
    - option "97080"
    - option "97086"
    - option "97089"
    - option "97101"
    - option "97102"
    - option "97103"
    - option "97106"
    - option "97107"
    - option "97110"
    - option "97111"
    - option "97112"
    - option "97113"
    - option "97114"
    - option "97115"
    - option "97116"
    - option "97117"
    - option "97118"
    - option "97119"
    - option "97122"
    - option "97123"
    - option "97124"
    - option "97125"
    - option "97127"
    - option "97128"
    - option "97130"
    - option "97131"
    - option "97132"
    - option "97133"
    - option "97134"
    - option "97135"
    - option "97136"
    - option "97138"
    - option "97140"
    - option "97141"
    - option "97143"
    - option "97146"
    - option "97147"
    - option "97148"
    - option "97149"
    - option "97201"
    - option "97202"
    - option "97203"
    - option "97205"
    - option "97206"
    - option "97209"
    - option "97210"
    - option "97211"
    - option "97212"
    - option "97213"
    - option "97214"
    - option "97215"
    - option "97216"
    - option "97217"
    - option "97218"
    - option "97219"
    - option "97220"
    - option "97221"
    - option "97222"
    - option "97223"
    - option "97224"
    - option "97225"
    - option "97227"
    - option "97229"
    - option "97230"
    - option "97231"
    - option "97232"
    - option "97233"
    - option "97236"
    - option "97239"
    - option "97266"
    - option "97267"
    - option "97301"
    - option "97302"
    - option "97303"
    - option "97304"
    - option "97305"
    - option "97306"
    - option "97317"
    - option "97321"
    - option "97322"
    - option "97324"
    - option "97325"
    - option "97327"
    - option "97330"
    - option "97333"
    - option "97335"
    - option "97338"
    - option "97341"
    - option "97342"
    - option "97345"
    - option "97346"
    - option "97347"
    - option "97348"
    - option "97350"
    - option "97351"
    - option "97352"
    - option "97355"
    - option "97357"
    - option "97358"
    - option "97361"
    - option "97362"
    - option "97364"
    - option "97365"
    - option "97366"
    - option "97367"
    - option "97368"
    - option "97369"
    - option "97370"
    - option "97371"
    - option "97374"
    - option "97376"
    - option "97378"
    - option "97381"
    - option "97383"
    - option "97386"
    - option "97388"
    - option "97391"
    - option "97392"
    - option "97394"
    - option "97396"
    - option "97401"
    - option "97402"
    - option "97403"
    - option "97404"
    - option "97405"
    - option "97408"
    - option "97410"
    - option "97411"
    - option "97412"
    - option "97413"
    - option "97415"
    - option "97416"
    - option "97417"
    - option "97420"
    - option "97423"
    - option "97424"
    - option "97426"
    - option "97431"
    - option "97434"
    - option "97435"
    - option "97436"
    - option "97437"
    - option "97439"
    - option "97441"
    - option "97442"
    - option "97443"
    - option "97444"
    - option "97446"
    - option "97448"
    - option "97449"
    - option "97450"
    - option "97451"
    - option "97452"
    - option "97453"
    - option "97454"
    - option "97455"
    - option "97456"
    - option "97457"
    - option "97458"
    - option "97459"
    - option "97461"
    - option "97462"
    - option "97463"
    - option "97465"
    - option "97466"
    - option "97467"
    - option "97469"
    - option "97470"
    - option "97471"
    - option "97477"
    - option "97478"
    - option "97479"
    - option "97481"
    - option "97484"
    - option "97486"
    - option "97487"
    - option "97488"
    - option "97490"
    - option "97492"
    - option "97493"
    - option "97495"
    - option "97496"
    - option "97497"
    - option "97498"
    - option "97499"
    - option "97501"
    - option "97502"
    - option "97503"
    - option "97504"
    - option "97520"
    - option "97523"
    - option "97524"
    - option "97526"
    - option "97527"
    - option "97530"
    - option "97532"
    - option "97537"
    - option "97540"
    - option "97541"
    - option "97601"
    - option "97603"
    - option "97621"
    - option "97622"
    - option "97624"
    - option "97625"
    - option "97636"
    - option "97637"
    - option "97638"
    - option "97639"
    - option "97641"
    - option "97701"
    - option "97702"
    - option "97703"
    - option "97707"
    - option "97720"
    - option "97731"
    - option "97733"
    - option "97734"
    - option "97735"
    - option "97738"
    - option "97739"
    - option "97741"
    - option "97753"
    - option "97754"
    - option "97756"
    - option "97759"
    - option "97801"
    - option "97810"
    - option "97812"
    - option "97814"
    - option "97818"
    - option "97820"
    - option "97823"
    - option "97827"
    - option "97828"
    - option "97830"
    - option "97833"
    - option "97834"
    - option "97835"
    - option "97836"
    - option "97838"
    - option "97840"
    - option "97842"
    - option "97843"
    - option "97844"
    - option "97845"
    - option "97846"
    - option "97848"
    - option "97850"
    - option "97856"
    - option "97857"
    - option "97859"
    - option "97862"
    - option "97865"
    - option "97867"
    - option "97869"
    - option "97875"
    - option "97877"
    - option "97880"
    - option "97882"
    - option "97885"
    - option "97886"
    - option "97914"
    - option "98070"
    - option "98082"
    - option "98221"
    - option "98310"
    - option "98346"
    - option "98531"
    - option "98532"
    - option "98550"
    - option "98564"
    - option "98565"
    - option "98572"
    - option "98581"
    - option "98582"
    - option "98591"
    - option "98593"
    - option "98596"
    - option "98601"
    - option "98603"
    - option "98604"
    - option "98605"
    - option "98606"
    - option "98607"
    - option "98610"
    - option "98611"
    - option "98612"
    - option "98613"
    - option "98614"
    - option "98616"
    - option "98619"
    - option "98620"
    - option "98623"
    - option "98624"
    - option "98625"
    - option "98626"
    - option "98628"
    - option "98629"
    - option "98631"
    - option "98632"
    - option "98635"
    - option "98639"
    - option "98640"
    - option "98642"
    - option "98644"
    - option "98645"
    - option "98648"
    - option "98650"
    - option "98651"
    - option "98660"
    - option "98661"
    - option "98662"
    - option "98663"
    - option "98664"
    - option "98665"
    - option "98670"
    - option "98671"
    - option "98672"
    - option "98673"
    - option "98674"
    - option "98675"
    - option "98682"
    - option "98683"
    - option "98684"
    - option "98685"
    - option "98686"
    - option "99322"
    - option "99328"
- text: Min Price
- 'link "Min Price: $200,000"':
  - /url: javascript:void(0)
- text: Min Price
- 'button "Min Price: $200,000"'
- textbox "Min Price": "200000"
- text: Max Price
- 'link "Max Price: $800,000"':
  - /url: javascript:void(0)
- text: Max Price
- 'button "Max Price: $800,000"'
- textbox "Max Price": "800000"
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
- text: Acres
- link "Acres":
  - /url: javascript:void(0)
- text: Acres
- button "Acres"
- textbox "Acres"
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
- text: Subdivision
- list:
  - listitem:
    - text: Subdivision
    - textbox "Subdivision"
- text: High School
- list:
  - listitem:
    - text: High School
    - textbox "High School"
- text: Middle Or Junior School
- list:
  - listitem:
    - text: Middle Or Junior School
    - textbox "Middle Or Junior School"
- text: Elementary School
- list:
  - listitem:
    - text: Elementary School
    - textbox "Elementary School"
- text: Remarks
- textbox "Remarks"
- text: Bank Owned
- radio "Yes"
- text: "Yes"
- radio "No"
- text: No Short Sale
- radio "Yes"
- text: "Yes"
- radio "No"
- text: No SqFt
- textbox "Min SqFt"
- text: to
- textbox "Max SqFt"
- text: Acres
- textbox "Min Acres"
- text: to
- textbox "Max Acres"
- text: Garage Type
- list:
  - listitem:
    - text: Garage Type
    - textbox "Garage Type"
- text: Neighborhood Features
- list:
  - listitem:
    - text: Neighborhood Features
    - textbox "Neighborhood Features"
- text: Exterior Description
- list:
  - listitem:
    - text: Exterior Description
    - textbox "Exterior Description"
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