<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-img
          :src="require('../assets/Saigon.png')"
          class="my-3"
          contain
          height="200"
        />
      </v-col>

      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          Welcome to Saigon Cafe
        </h1>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <v-card>
          <v-tabs v-model="tab" fixed-tabs background-color="secondary">
            <v-tab>About</v-tab>
            <v-tab>Menu</v-tab>
          </v-tabs>
          <v-tabs-items v-model="tab" style="background-color: #f5f5c9">
            <v-tab-item>
              <v-card-text>
                <v-row>
                  <v-col>
                    <v-card style="background-color: #f5f5d5">
                      <v-card-title>
                        Contact:
                      </v-card-title>
                      <v-card-text>
                        (801) 812 - 1173
                        <br/>
                        email@email.com
                      </v-card-text>
                    </v-card>
                    <br/>
                    <v-card style="background-color: #f5f5d5">
                      <v-card-title>
                        Hours:
                      </v-card-title>
                      <v-card-text>
                        Monday - Thursday: 11:00 AM - 10:00 PM
                        <br/>
                        Friday - Saturday: 11:00 AM - 10:30 PM
                        <br/>
                        Sunday: Closed
                      </v-card-text>
                    </v-card>
                    <br/>
                    <v-card style="background-color: #f5f5d5">
                      <v-card-title>
                        Delivery:
                      </v-card-title>
                      <v-card-text>
                        Delivery free to Provo area
                        <br/>
                        Minimum order of $18.00 required for delivery
                        <br/>
                        Monday - Thursday: 11:00 AM - 9:00 PM
                        <br/>
                        Friday - Saturday: 11:00 AM - 9:30 PM
                      </v-card-text>
                    </v-card>
                    <br/>
                    <v-card style="background-color: #f5f5d5">
                      <v-card-text>
                        Menu prices, hours, and others are subject to change without notice
                      </v-card-text>
                    </v-card>
                  </v-col>
                  <v-col>
                    <iframe src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d12184.246702850241!2d-111.6665108!3d40.2299309!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x50ca5d3214f09170!2sSaigon%20Cafe!5e0!3m2!1sen!2sus!4v1619076887155!5m2!1sen!2sus" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
                  </v-col>
                </v-row>
              </v-card-text>
            </v-tab-item>
            <v-tab-item>
              <v-card-text v-for="item in items" :key="item.number">
                <v-card style="background-color: #f5f5d5">
                  <v-card-title @click="item.show = !item.show">{{ item.chinese }} - {{ item.name }}:</v-card-title>
                  <v-expand-transition>
                    <div v-show="item.show">
                      <v-divider></v-divider>
                      <v-list style="background-color: #f2f2dc" dense>
                        <v-list-item-group
                            v-model="selectedItem"
                            color="secondary"
                        >
                        <v-list-item
                            v-for="(current, i) in item.children"
                            :key="i"
                        >
                          <v-list-item-content>
                            <v-list-item-title>{{ current.number }} - {{ current.name }}</v-list-item-title>
                            <v-list-item-subtitle>{{ current.price }}</v-list-item-subtitle>
                          </v-list-item-content>
                        </v-list-item>
                        </v-list-item-group>
                      </v-list>
                    </div>
                  </v-expand-transition>
                </v-card>
              </v-card-text>

              <div id="SS274102vv7SLxIbu-anchor" class="ssWidgetBox ss-block text-container" style="background-color: rgb(3, 78, 47); font-family: Tahoma; position: relative; top: 0px; left: 0px;"><div class="widget-container type-text normal" id="SS274102vv7SLxIbu" style="display: block;"><div class="title-bar" style="color: rgb(255, 255, 255); border-color: rgb(177, 232, 175);"><img class="widget-title-icon" style="display:none;"><span class="widget-title">Menu</span><div class="navigation"><span class="close" onclick=""></span></div></div><div class="loading-text" style="position: relative; text-align: center; top: 0px; left: 0px; display: none;">Loading...</div><div class="widget-instance ui-gdTextSS274102vv7SLxIbu ui-gdText" id="SS274102vv7SLxIbu-text-normal" style="top: 0px; left: 0px; color: rgb(255, 255, 255);"><div class="ui-gdText-container" style="color: rgb(255, 255, 255);">



                <h1 style="color: rgb(255, 255, 255);"><p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-family: &quot;Times New Roman&quot;, serif; font-size: 13.5pt; color: rgb(255, 255, 255);">No Substitution</span></p><p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-family: &quot;Times New Roman&quot;, serif; font-size: 13.5pt; color: rgb(255, 255, 255);">Soup</span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">1. Wonton
Soup..........................................$6.75<br>
2. Egg Drop Soup.......................................$4.95<br>
3. Hot &amp; Sour Soup....................................$4.95<br>
4. Assorted Vegetable Soup.......................$4.95<br>
5. House Seafood Soup..............................$7.50<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Appetizers<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">6. Steamed Spring Rolls
(3)......................$5.45<br>
7. Egg Rolls (4).........................................$4.25<br>
8. Fried Cheese Wonton (10)…………....$4.25<br>
9. Meat Wonton (10).................................$5.45<br>
10. Deep Fried Jumbo Shrimp..................$6.95<br>
11. B.B.Q Pork..........................................$6.95<br>
12. Pot stickers (6)....................................$4.95<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Fried Rice<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">13. Chicken Fried Rice…………..............$6.25<br>
14. Roast Pork Fried Rice.........................$6.95<br>
15. Ham Fried Rice....................................$5.95<br>
16. Beef Fried Rice.....................................$6.95<br>
17.Shrimp Fried Rice.................................$7.50<br>
18. House Special Fried Rice.....................$7.50<br>
19. Hong Kong Style Fried Rice………...$7.50<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Pan Fried Noodles<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">20. Chicken Pan Fried
Noodles...............$7.95<br>
21. BBQ Pork Pan Fried Noodles……....$8.50<br>
22. Vegetable&nbsp;Pan Fried Noodles.............$7.25<br>
23. Beef Pan Fried Noodles......................$8.50<br>
24. Shrimp Pan Fried Noodles.................$8.95<br>
25. House Special Pan Fried&nbsp;Noodles…..$8.95&nbsp;<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);"><br>
<br>
Lo Mein<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">26. Chicken Lo
Mein.......................$6.75<br>
27. Roast Pork Lo Mein..................$7.25<br>
28. Vegetable Lo Mein.....................$6.25<br>
29. Beef Lo Mein..............................$7.25<br>
30. Shrimp Lo Mein.........................$7.75<br>
31. House Special Lo Mein..............$7.75<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Crunchy Chow Mein<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">32. Chicken Chow
Mein.................$6.75<br>
33. Roast Pork Chow Mein............$7.25<br>
34. Vegetable Chow Mein...............$6.25<br>
35. Beef Chow Mein........................$7.25<br>
36. Shrimp Chow Mein...................$7.75<br>
37. House Special Chow Mein…....$7.75<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Chicken (comes with
steamed rice)<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">$7.50<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">38. Cashew Nut Chicken<br>
39. Mu Shu Chicken<br>
40. Moo Goo Gai Pan<br>
41. Broccoli Chicken<br>
42. Vegetable Chicken<br>
43. Sweet &amp; Sour Chicken<br>
44. Lemon Chicken<br>
45. Snow Peas Chicken<br>
46. Sesame Chicken<br>
47. Kung Pao Chicken<br>
48. Chicken w. Garlic Sauce<br>
49. Curry Chicken<br>
50. Chicken in Black Bean Sauce<br>
51. Szechuan Chicken<br>
52. General Tso's Chicken<br>
53. Orange Chicken<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Beef (comes with steamed
rice)<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">$8.25<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">54. Vegetable Beef<br>
55. Broccoli with&nbsp; Beef<br>
56. Beef with Snow Peas<br>
57. Mongolian&nbsp; Beef<br>
58. Ma Pa Tofu<br>
59. Kung Pao&nbsp; Beef<br>
60. Beef in Garlic Sauce<br>
61. Szechuan&nbsp; Beef<br>
62. Beef in Black Bean Sauce<br>
63. Curry&nbsp; Beef<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Pork (comes with white
rice)<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">$7.50<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">64. Pork in Garlic Sauce<br>
65. Sweet &amp; Sour Pork<br>
66. Moo Shu Pork<br>
67. BBQ Pork w/Broccoli<br>
68. BBQ Pork w/ Snow Peas<br>
69. BBQ Pork w/ Vegetables<br>
70. Kung Pao Pork<br>
71. Szechuan Pork<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Shrimp (comes with white
rice)<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">$8.95<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">72. Shrimp w/ Cashew
Nuts<br>
73. Shrimp w/ Vegetables<br>
74. Shrimp w/ Snow Peas<br>
75. Sweet &amp; Sour Shrimp<br>
76. Kung Pao Shrimp<br>
77. Szechuan Shrimp<br>
78. Shrimp in Garlic Sauce<br>
79. Shrimp in Curry Sauce<br>
80. Shrimp in Black Bean Sauce<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Vegetable (comes with
white rice)<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">81. Baby bok Choy w
Oyster Sauce.......$6.95<br>
82. Grandma's Bean Curd.....................$6.95<br>
83. Braised Bean Curd...........................$6.95<br>
84. Mixed Vegetables..............................$6.75<br>
85. Kung Pao Vegetables........................$6.75<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Egg Foo Young (comes
with white rice)<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">86.&nbsp;Chicken Egg Foo
Young..................$6.95<br>
87.&nbsp;BBQ Egg Foo Young.......................$7.25<br>
88. Ham Egg Foo Young.......................$6.75<br>
89. Beef Egg Foo Young........................$7.25<br>
90. Shrimp Egg Foo&nbsp;Young...................$7.65<br>
91.&nbsp;Vegetable Egg Foo Young...............$6.75<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Sizzling Platter (comes
with&nbsp;white&nbsp;rice)<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">92. Vegetable
Sizzling&nbsp;Platter....................$7.95<br>
93. Chicken Sizzling&nbsp;Platter......................$8.75<br>
94. Beef Sizzling&nbsp;Platter.............................$8.95<br>
95. Shrimp Sizzling Platter.......................$9.95<br>
                    <!--[if !supportLineBreakNewLine]--><br>
                    <!--[endif]--><o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Noodle Soups (Egg Noodle
additional $1.00)<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);"><br>
96. Beef &amp; Meatball Noodle Soup……..$6.75<br>
97. Beef Meatball Noodle Soup..............$5.95<br>
98. Rare Cooked Beef Noodle Soup……$6.25<br>
99. Chicken Noodle Soup........................$6.25<br>
100. Shrimp Noodle Soup……………...$6.75<br>
101. Vegetable&nbsp;Noodle Soup...................$5.95<br>
102. Pork Wonton Noodle Soup.............$7.25<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Chef Special's<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">103. CHICKEN, BEEF OR
B.B.Q. PORK FLAT NOODLE ..............$9.50<br>
SHRIMP ADD $1.00<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">104. SINGAPORE RICE
NOODLE .......................................................$9.50<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">105. KUNG PAO CHICKEN
&amp; SHRIMP............................................... $9.50<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">106. SHRIMP W/ WALNUT IN
MAYONNAISE SAUCE&nbsp; ..................$12.95&nbsp;<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">107. DELUXE
SIZZLING&nbsp; PLATTER ...................................................$11.95<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">S9.HAPPY&nbsp;
FAMILY&nbsp; ...............................................................................
$11.95<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">SPECIAL&nbsp;
COMBINATION<br>
(Served w/ Soup, Ham Fried Rice, &amp; Egg Roll)&nbsp;<br>
No change available<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">$6.50
(Chicken/Pork/Vegetable) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $6.75 (Beef)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
$7.25(Shrimp)<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">C1. Chow Mein (Crispy
Noodles) with Chicken, Shrimp or Veg.<br>
C2. Lo Mein (Soft&nbsp; Noodles) with Chicken, Pork, Beef, Shrimp or Veg.<br>
C3. Green Pepper &amp; Black Bean Sauce with Chicken, Beef or Shrimp.<br>
C4. Orange Chicken<br>
C5. Mongolian Beef<br>
C6. Sesame Chicken<br>
C7. Kung Pao Chicken or Shrimp<br>
C8. Moo Goo Gai Pan (Chicken w/ Mushroom)<br>
C9. Garlic Sauce with Chicken or Shrimp<br>
C10. General Tso’s Chicken<br>
C11. Lemon Chicken<br>
C12. Cashew Nut with Chicken or Shrimp<br>
C13. Broccoli with (Beef, Chicken or Shrimp)<br>
C14. Sweet &amp; Sour (Pork, Chicken or Shrimp)<br>
                    <!--[if !supportLineBreakNewLine]--><br>
                    <!--[endif]--><o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Family Value Meals
Family Value Meals<br>
$9.75 per person<br>
(Minimum for 2 people)<br>
Includes: Soup of the Day, Ham Fried Rice, Egg Roll, Cheese Wonton.&nbsp;<br>
Choice of one dish per person (1 chicken, beef or pork dish)<br>
(Shrimp Entree add $2.00 per person)<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">&nbsp;<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Side Orders<o:p></o:p></span></p>

                  <p style="line-height: normal; color: rgb(255, 255, 255);"><span style="font-size: 13.5pt; font-family: &quot;Times New Roman&quot;, serif; color: rgb(255, 255, 255);">Steam Rice Small&nbsp;
(16 oz. ) ............$1.50<br>
Steam Rice Large&nbsp; (32 oz.)..............$3.00<br>
Wonton Skins...................................$2.00<br>
Cup of Egg Drop Soup ...................$1.50<br>
Cup of Hot &amp; Sour Soup................ $1.50<br>
Drinks…………………………...….$1.95<br>
&nbsp;<br>
<br>
&nbsp;<o:p></o:p></span></p>

                  <p style="color: rgb(255, 255, 255);"><o:p>&nbsp;</o:p></p></h1>



              </div></div></div></div>
            </v-tab-item>
          </v-tabs-items>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'Main',

    data: () => ({
      tab: 0,
      show: false,
      selectedItem: {},
      items: [
        {
          id: 1, name: 'Soup', chinese: '湯類', show: false, children: [
            { name: 'Wonton Soup', number: 1, price: '$6.75', hot: false, category: 'soup' },
            { name: 'Egg Drop Soup', number: 2, price: '$4.95', hot: false, category: 'soup' },
            { name: 'Hot & Sour Soup', number: 3, price: '$4.95', hot: true, category: 'soup' },
            { name: 'Assorted Vegetable Soup', number: 4, price: '$4.95', hot: false, category: 'soup' },
            { name: 'House Seafood Soup', number: 5, price: '$7.50', hot: false, category: 'soup' },
          ]
        },
        {
          id: 2, name: 'Appetizers', show: false, children: [
            { name: 'Steamed Spring Rolls (3)', number: 6, price: '$5.45', hot: false, category: 'appetizers' },
            { name: 'Egg Rolls (4)', number: 7, price: '$4.45', hot: false, category: 'appetizers' },
            { name: 'Fried Cheese Wontons (10)', number: 8, price: '$4.95', hot: false, category: 'appetizers' },
            { name: 'Meat Wontons (10)', number: 9, price: '$5.45', hot: false, category: 'appetizers' },
            { name: 'Deep Fried Jumbo Shrimp (5)', number: 10, price: '$6.95', hot: false, category: 'appetizers' },
            { name: 'BBQ Pork', number: 11, price: '$6.95', hot: false, category: 'appetizers' },
            { name: 'Pot Stickers (6)', number: 12, price: '$4.95', hot: false, category: 'appetizers' },
          ]
        },
        {
          id: 3, name: 'Fried Rice', chinese: '', show: false, children: [
            { name: 'Chicken Fried Rice', number: 13, price: '$6.25', hot: false, category: 'friedRice' },
            { name: 'Roast Pork Fried Rice', number: 14, price: '$6.95', hot: false, category: 'friedRice' },
            { name: 'Ham Fried Rice', number: 15, price: '$5.95', hot: false, category: 'friedRice' },
            { name: 'Beef Fried Rice', number: 16, price: '$6.95', hot: false, category: 'friedRice' },
            { name: 'Shrimp Fried Rice', number: 17, price: '$7.50', hot: false, category: 'friedRice' },
            { name: 'House Special Fried Rice', number: 18, price: '$7.50', hot: false, category: 'friedRice' },
            { name: 'Hong Kong Style Fried Rice', number: 19, price: '$7.50', hot: false, category: 'friedRice' },
          ]
        },
        {
          id: 4, name: 'Pan Fried Noodles', chinese: '', show: false, children: [
            { name: 'Chicken Pan Fried Noodles', number: 20, price: '$7.95', hot: false, category: 'friedNoodles' },
            { name: 'BBQ Pork Pan Fried Noodles', number: 21, price: '$8.50', hot: false, category: 'friedNoodles' },
            { name: 'Vegetable Pan Fried Noodles', number: 22, price: '$7.25', hot: false, category: 'friedNoodles' },
            { name: 'Beef Pan Fried Noodles', number: 23, price: '$8.50', hot: false, category: 'friedNoodles' },
            { name: 'Shrimp Pan Fried Noodles', number: 24, price: '$8.95', hot: false, category: 'friedNoodles' },
            { name: 'House Special Pan Fried Noodles', number: 25, price: '$8.95', hot: false, category: 'friedNoodles' },
          ]
        },
        {
          id: 5, name: 'Lo Mein', chinese: '', show: false, children: [
            { name: 'Chicken Lo Mein', number: 26, price: '$6.75', hot: false, category: 'loMein' },
            { name: 'Roast Pork Lo Mein', number: 27, price: '$7.25', hot: false, category: 'loMein' },
            { name: 'Vegetable Lo Mein', number: 28, price: '$6.25', hot: false, category: 'loMein' },
            { name: 'Beef Lo Mein', number: 29, price: '$7.25', hot: false, category: 'loMein' },
            { name: 'Shrimp Lo Mein', number: 30, price: '$7.75', hot: false, category: 'loMein' },
            { name: 'House Special Lo Mein', number: 31, price: '$7.75', hot: false, category: 'loMein' },
          ]
        },
        {
          id: 6, name: 'Crunchy Chow Mein', chinese: '', show: false, children: [
            { name: 'Chicken Chow Mein', number: 32, price: '$6.75', hot: false, category: 'chowMein' },
            { name: 'Roast Pork Chow Mein', number: 33, price: '$7.25', hot: false, category: 'chowMein' },
            { name: 'Vegetable Chow Mein', number: 34, price: '$6.25', hot: false, category: 'chowMein' },
            { name: 'Beef Chow Mein', number: 35, price: '$7.25', hot: false, category: 'chowMein' },
            { name: 'Shrimp Chow Mein', number: 36, price: '$7.75', hot: false, category: 'chowMein' },
            { name: 'House Special Chow Mein', number: 37, price: '$7.75', hot: false, category: 'chowMein' },
          ]
        },
        {
          id: 7, name: 'Chicken', chinese: '', tooltip: '(comes with steamed rice)', show: false, children: [
            { name: 'Pot Stickers (6)', number: 38, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 39, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 40, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 41, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 42, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 43, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 44, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 45, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 46, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 47, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 48, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 49, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 50, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 51, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 52, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Pot Stickers (6)', number: 53, price: '$7.50', hot: false, category: 'chicken' },
          ]
        },
        {
          id: 8, name: 'Beef', chinese: '', tooltip: '(comes with steamed rice)', show: false, children: [
            { name: 'Pot Stickers (6)', number: 54, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Pot Stickers (6)', number: 55, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Pot Stickers (6)', number: 56, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Pot Stickers (6)', number: 57, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Pot Stickers (6)', number: 58, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Pot Stickers (6)', number: 59, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Pot Stickers (6)', number: 60, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Pot Stickers (6)', number: 61, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Pot Stickers (6)', number: 62, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Pot Stickers (6)', number: 63, price: '$8.25', hot: false, category: 'beef' },
          ]
        },
        {
          id: 9, name: 'Pork', chinese: '', tooltip: '(comes with steamed rice)', show: false, children: [
            { name: 'Pot Stickers (6)', number: 64, price: '$7.50', hot: false, category: 'pork' },
            { name: 'Pot Stickers (6)', number: 65, price: '$7.50', hot: false, category: 'pork' },
            { name: 'Pot Stickers (6)', number: 66, price: '$7.50', hot: false, category: 'pork' },
            { name: 'Pot Stickers (6)', number: 67, price: '$7.50', hot: false, category: 'pork' },
            { name: 'Pot Stickers (6)', number: 68, price: '$7.50', hot: false, category: 'pork' },
            { name: 'Pot Stickers (6)', number: 69, price: '$7.50', hot: false, category: 'pork' },
            { name: 'Pot Stickers (6)', number: 70, price: '$7.50', hot: false, category: 'pork' },
            { name: 'Pot Stickers (6)', number: 71, price: '$7.50', hot: false, category: 'pork' },
          ]
        },
        {
          id: 10, name: 'Shrimp', chinese: '', tooltip: '(comes with steamed rice)', show: false, children: [
            { name: 'Pot Stickers (6)', number: 72, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Pot Stickers (6)', number: 73, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Pot Stickers (6)', number: 74, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Pot Stickers (6)', number: 75, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Pot Stickers (6)', number: 76, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Pot Stickers (6)', number: 77, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Pot Stickers (6)', number: 78, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Pot Stickers (6)', number: 79, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Pot Stickers (6)', number: 80, price: '$8.95', hot: false, category: 'shrimp' },
          ]
        },
        {
          id: 11, name: 'Vegetable', chinese: '', tooltip: '(comes with steamed rice)', show: false, children: [
            { name: 'Pot Stickers (6)', number: 81, price: '$6.95', hot: false, category: 'vegetable' },
            { name: 'Pot Stickers (6)', number: 82, price: '$6.95', hot: false, category: 'vegetable' },
            { name: 'Pot Stickers (6)', number: 83, price: '$6.95', hot: false, category: 'vegetable' },
            { name: 'Pot Stickers (6)', number: 84, price: '$6.75', hot: false, category: 'vegetable' },
            { name: 'Pot Stickers (6)', number: 85, price: '$6.75', hot: false, category: 'vegetable' },
          ]
        },
        {
          id: 12, name: 'Egg Foo Young', chinese: '', tooltip: '(comes with steamed rice)', show: false, children: [
            { name: 'Pot Stickers (6)', number: 86, price: '$6.95', hot: false, category: 'eggFoo' },
            { name: 'Pot Stickers (6)', number: 87, price: '$7.25', hot: false, category: 'eggFoo' },
            { name: 'Pot Stickers (6)', number: 88, price: '$6.75', hot: false, category: 'eggFoo' },
            { name: 'Pot Stickers (6)', number: 89, price: '$7.25', hot: false, category: 'eggFoo' },
            { name: 'Pot Stickers (6)', number: 90, price: '$7.65', hot: false, category: 'eggFoo' },
            { name: 'Pot Stickers (6)', number: 91, price: '$6.75', hot: false, category: 'eggFoo' },
          ]
        },
        {
          id: 13, name: 'Sizzling Platter', chinese: '', tooltip: '(comes with steamed rice)', show: false, children: [
            { name: 'Pot Stickers (6)', number: 92, price: '$7.95', hot: false, category: 'sizzling' },
            { name: 'Pot Stickers (6)', number: 93, price: '$8.75', hot: false, category: 'sizzling' },
            { name: 'Pot Stickers (6)', number: 94, price: '$8.95', hot: false, category: 'sizzling' },
            { name: 'Pot Stickers (6)', number: 95, price: '$9.95', hot: false, category: 'sizzling' },
          ]
        },
        {
          id: 14, name: 'Noodle Soup', chinese: '', tooltip: '(Egg Noodle additional $1.00)', show: false, children: [
            { name: 'Pot Stickers (6)', number: 96, price: '$6.75', hot: false, category: 'noodleSoup' },
            { name: 'Pot Stickers (6)', number: 97, price: '$5.95', hot: false, category: 'noodleSoup' },
            { name: 'Pot Stickers (6)', number: 98, price: '$6.25', hot: false, category: 'noodleSoup' },
            { name: 'Pot Stickers (6)', number: 99, price: '$6.25', hot: false, category: 'noodleSoup' },
            { name: 'Pot Stickers (6)', number: 100, price: '$6.75', hot: false, category: 'noodleSoup' },
            { name: 'Pot Stickers (6)', number: 101, price: '$5.95', hot: false, category: 'noodleSoup' },
            { name: 'Pot Stickers (6)', number: 102, price: '$7.25', hot: false, category: 'noodleSoup' },
          ]
        },
        {
          id: 15, name: 'Chef Specials', chinese: '', show: false, children: [
            { name: 'Pot Stickers (6)', number: 103, price: '$9.50', hot: false, category: 'specials' },
            { name: 'Pot Stickers (6)', number: 104, price: '$9.50', hot: false, category: 'specials' },
            { name: 'Pot Stickers (6)', number: 105, price: '$9.50', hot: false, category: 'specials' },
            { name: 'Pot Stickers (6)', number: 106, price: '$12.95', hot: false, category: 'specials' },
            { name: 'Pot Stickers (6)', number: 107, price: '$11.95', hot: false, category: 'specials' },
            { name: 'Pot Stickers (6)', number: 108, price: '$11.95', hot: false, category: 'specials' },
          ]
        },
        {
          id: 16, name: 'Special Combinations', chinese: '', show: false, children: [
            { name: 'Pot Stickers (6)', number: 1, price: '$4.95', hot: false, category: 'combination' },
            { name: 'Pot Stickers (6)', number: 2, price: '$4.95', hot: false, category: 'combination' },
            { name: 'Pot Stickers (6)', number: 3, price: '$4.95', hot: false, category: 'combination' },
            { name: 'Pot Stickers (6)', number: 4, price: '$4.95', hot: false, category: 'combination' },
            { name: 'Pot Stickers (6)', number: 5, price: '$4.95', hot: false, category: 'combination' },
            { name: 'Pot Stickers (6)', number: 6, price: '$4.95', hot: false, category: 'combination' },
            { name: 'Pot Stickers (6)', number: 7, price: '$4.95', hot: false, category: 'combination' },
            { name: 'Pot Stickers (6)', number: 8, price: '$4.95', hot: false, category: 'combination' },
            { name: 'Pot Stickers (6)', number: 9, price: '$4.95', hot: false, category: 'combination' },
            { name: 'Pot Stickers (6)', number: 10, price: '$4.95', hot: false, category: 'combination' },
            { name: 'Pot Stickers (6)', number: 11, price: '$4.95', hot: false, category: 'combination' },
            { name: 'Pot Stickers (6)', number: 12, price: '$4.95', hot: false, category: 'combination' },
            { name: 'Pot Stickers (6)', number: 13, price: '$4.95', hot: false, category: 'combination' },
            { name: 'Pot Stickers (6)', number: 14, price: '$4.95', hot: false, category: 'combination' },
          ]
        },
        {
          id: 17, name: 'Family Value Meals', chinese: '', show: false, children: [
            { name: 'Pot Stickers (6)', price: '$4.95', hot: false, category: 'family' },
          ]
        },
        {
          id: 18, name: 'Side Orders', chinese: '', show: false, children: [
            { name: 'Pot Stickers (6)', price: '$1.50', hot: false, category: 'side' },
            { name: 'Pot Stickers (6)', price: '$3.00', hot: false, category: 'side' },
            { name: 'Pot Stickers (6)', price: '$2.00', hot: false, category: 'side' },
            { name: 'Pot Stickers (6)', price: '$1.50', hot: false, category: 'side' },
            { name: 'Pot Stickers (6)', price: '$1.50', hot: false, category: 'side' },
            { name: 'Pot Stickers (6)', price: '$1.95', hot: false, category: 'side' },
          ]
        }
      ]
    }),
  }
</script>
