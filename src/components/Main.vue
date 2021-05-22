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
                  <v-card-subtitle @click="item.show = !item.show">{{ item.tooltip }}</v-card-subtitle>
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
            { name: 'Cashew Nut Chicken', number: 38, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Mu Shu Chicken', number: 39, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Moo Goo Gai Pan', number: 40, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Broccoli Chicken', number: 41, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Vegetable Chicken', number: 42, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Sweet & Sour Chicken', number: 43, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Lemon Chicken', number: 44, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Snow Peas Chicken', number: 45, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Sesame Chicken', number: 46, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Kung Pao Chicken', number: 47, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Chicken with Garlic Sauce', number: 48, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Curry Chicken', number: 49, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Chicken in Black Bean Sauce', number: 50, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Szechuan Chicken', number: 51, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'General Tso\'s Chicken', number: 52, price: '$7.50', hot: false, category: 'chicken' },
            { name: 'Orange Chicken', number: 53, price: '$7.50', hot: false, category: 'chicken' },
          ]
        },
        {
          id: 8, name: 'Beef', chinese: '', tooltip: '(comes with steamed rice)', show: false, children: [
            { name: 'Vegetable Beef', number: 54, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Broccoli with Beef', number: 55, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Beef with Snow Peas', number: 56, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Mongolian Beef', number: 57, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Ma Pa Tofu', number: 58, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Kung Pao Beef', number: 59, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Beef in Garlic Sauce', number: 60, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Szechuan Beef', number: 61, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Beef in Black Bean Sauce', number: 62, price: '$8.25', hot: false, category: 'beef' },
            { name: 'Curry Beef', number: 63, price: '$8.25', hot: false, category: 'beef' },
          ]
        },
        {
          id: 9, name: 'Pork', chinese: '', tooltip: '(comes with steamed rice)', show: false, children: [
            { name: 'Pork in Garlic Sauce', number: 64, price: '$7.50', hot: false, category: 'pork' },
            { name: 'Sweet & Sour Pork', number: 65, price: '$7.50', hot: false, category: 'pork' },
            { name: 'Moo Shu Pork', number: 66, price: '$7.50', hot: false, category: 'pork' },
            { name: 'BBQ Pork with Broccoli', number: 67, price: '$7.50', hot: false, category: 'pork' },
            { name: 'BBQ Pork with Snow Peas', number: 68, price: '$7.50', hot: false, category: 'pork' },
            { name: 'BBQ Pork with Vegetables', number: 69, price: '$7.50', hot: false, category: 'pork' },
            { name: 'Kung Pao Pork', number: 70, price: '$7.50', hot: false, category: 'pork' },
            { name: 'Szechuan Pork', number: 71, price: '$7.50', hot: false, category: 'pork' },
          ]
        },
        {
          id: 10, name: 'Shrimp', chinese: '', tooltip: '(comes with steamed rice)', show: false, children: [
            { name: 'Shrimp with Cashew Nuts', number: 72, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Shrimp with Vegetables', number: 73, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Shrimp with Snow Peas', number: 74, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Sweet & Sour Shrimp', number: 75, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Kung Pao Shrimp', number: 76, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Szechuan Shrimp', number: 77, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Shrimp in Garlic Sauce', number: 78, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Shrimp in Curry Sauce', number: 79, price: '$8.95', hot: false, category: 'shrimp' },
            { name: 'Shrimp in Black Bean Sauce', number: 80, price: '$8.95', hot: false, category: 'shrimp' },
          ]
        },
        {
          id: 11, name: 'Vegetable', chinese: '', tooltip: '(comes with steamed rice)', show: false, children: [
            { name: 'Baby Bok Choy with Oyster Sauce', number: 81, price: '$6.95', hot: false, category: 'vegetable' },
            { name: 'Grandma\'s Bean Curd', number: 82, price: '$6.95', hot: false, category: 'vegetable' },
            { name: 'Braised Bean Curd', number: 83, price: '$6.95', hot: false, category: 'vegetable' },
            { name: 'Mixed Vegetables', number: 84, price: '$6.75', hot: false, category: 'vegetable' },
            { name: 'Kung Pao Vegetables', number: 85, price: '$6.75', hot: false, category: 'vegetable' },
          ]
        },
        {
          id: 12, name: 'Egg Foo Young', chinese: '', tooltip: '(comes with steamed rice)', show: false, children: [
            { name: 'Chicken Egg Foo Young', number: 86, price: '$6.95', hot: false, category: 'eggFoo' },
            { name: 'BBQ Egg Foo Young', number: 87, price: '$7.25', hot: false, category: 'eggFoo' },
            { name: 'Ham Egg Foo Young', number: 88, price: '$6.75', hot: false, category: 'eggFoo' },
            { name: 'Beef Egg Foo Young', number: 89, price: '$7.25', hot: false, category: 'eggFoo' },
            { name: 'Shrimp Egg Foo Young', number: 90, price: '$7.65', hot: false, category: 'eggFoo' },
            { name: 'Vegetable Egg Foo Young', number: 91, price: '$6.75', hot: false, category: 'eggFoo' },
          ]
        },
        {
          id: 13, name: 'Sizzling Platter', chinese: '', tooltip: '(comes with steamed rice)', show: false, children: [
            { name: 'Vegetable Sizzling Platter', number: 92, price: '$7.95', hot: false, category: 'sizzling' },
            { name: 'Chicken Sizzling Platter', number: 93, price: '$8.75', hot: false, category: 'sizzling' },
            { name: 'Beef Sizzling Platter', number: 94, price: '$8.95', hot: false, category: 'sizzling' },
            { name: 'Shrimp Sizzling Platter', number: 95, price: '$9.95', hot: false, category: 'sizzling' },
          ]
        },
        {
          id: 14, name: 'Noodle Soup', chinese: '', tooltip: '(Egg Noodle additional $1.00)', show: false, children: [
            { name: 'Beef & Meatball Noodle Soup', number: 96, price: '$6.75', hot: false, category: 'noodleSoup' },
            { name: 'Beef Meatball Noodle Soup', number: 97, price: '$5.95', hot: false, category: 'noodleSoup' },
            { name: 'Rare Cooked Beef Noodle Soup', number: 98, price: '$6.25', hot: false, category: 'noodleSoup' },
            { name: 'Chicken Noodle Soup', number: 99, price: '$6.25', hot: false, category: 'noodleSoup' },
            { name: 'Shrimp Noodle Soup', number: 100, price: '$6.75', hot: false, category: 'noodleSoup' },
            { name: 'Vegetable Noodle Soup', number: 101, price: '$5.95', hot: false, category: 'noodleSoup' },
            { name: 'Pork Wonton Noodle Soup', number: 102, price: '$7.25', hot: false, category: 'noodleSoup' },
          ]
        },
        {
          id: 15, name: 'Chef Specials', chinese: '', show: false, children: [
            { name: 'placeholder', number: 103, price: '$9.50', hot: false, category: 'specials' },
            { name: 'placeholder', number: 104, price: '$9.50', hot: false, category: 'specials' },
            { name: 'placeholder', number: 105, price: '$9.50', hot: false, category: 'specials' },
            { name: 'placeholder', number: 106, price: '$12.95', hot: false, category: 'specials' },
            { name: 'placeholder', number: 107, price: '$11.95', hot: false, category: 'specials' },
            { name: 'placeholder', number: 108, price: '$11.95', hot: false, category: 'specials' },
          ]
        },
        {
          id: 16, name: 'Special Combinations', chinese: '', show: false, children: [
            { name: 'placeholder', number: 1, price: '$4.95', hot: false, category: 'combination' },
            { name: 'placeholder', number: 2, price: '$4.95', hot: false, category: 'combination' },
            { name: 'placeholder', number: 3, price: '$4.95', hot: false, category: 'combination' },
            { name: 'placeholder', number: 4, price: '$4.95', hot: false, category: 'combination' },
            { name: 'placeholder', number: 5, price: '$4.95', hot: false, category: 'combination' },
            { name: 'placeholder', number: 6, price: '$4.95', hot: false, category: 'combination' },
            { name: 'placeholder', number: 7, price: '$4.95', hot: false, category: 'combination' },
            { name: 'placeholder', number: 8, price: '$4.95', hot: false, category: 'combination' },
            { name: 'placeholder', number: 9, price: '$4.95', hot: false, category: 'combination' },
            { name: 'placeholder', number: 10, price: '$4.95', hot: false, category: 'combination' },
            { name: 'placeholder', number: 11, price: '$4.95', hot: false, category: 'combination' },
            { name: 'placeholder', number: 12, price: '$4.95', hot: false, category: 'combination' },
            { name: 'placeholder', number: 13, price: '$4.95', hot: false, category: 'combination' },
            { name: 'placeholder', number: 14, price: '$4.95', hot: false, category: 'combination' },
          ]
        },
        {
          id: 17, name: 'Family Value Meals', chinese: '', show: false, children: [
            { name: 'placeholder', price: '$4.95', hot: false, category: 'family' },
          ]
        },
        {
          id: 18, name: 'Side Orders', chinese: '', show: false, children: [
            { name: 'Steam Rice Small (16oz)', price: '$1.50', hot: false, category: 'side' },
            { name: 'Steam Rice Large (32oz)', price: '$3.00', hot: false, category: 'side' },
            { name: 'Wonton Skins', price: '$2.00', hot: false, category: 'side' },
            { name: 'Cup of Egg Drop Soup', price: '$1.50', hot: false, category: 'side' },
            { name: 'Cup of Hot & Sour Soup', price: '$1.50', hot: false, category: 'side' },
            { name: 'Drinks', price: '$1.95', hot: false, category: 'side' },
          ]
        }
      ]
    }),
  }
</script>
