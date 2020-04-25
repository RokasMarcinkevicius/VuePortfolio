<template>
  <v-app id="inspire">
    <v-navigation-drawer
            v-model="drawer"
            app
            clipped
    >
      <v-list rounded>
        <v-list>
          <v-list-item
                  v-for="item in items2"
                  :key="item.text"
                  link
          >
            <v-list-item-avatar size="60">
              <img
                      :src="`https://cdn.vuetifyjs.com/images/john.jpg`"
                      alt=""

              >
            </v-list-item-avatar>
            <v-list-item-title v-text="item.text" />
          </v-list-item>
        </v-list>

        <v-list-item
                v-for="item in items"
                :key="item.text"
                link
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>
              {{ item.text }}
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>

    </v-navigation-drawer>

    <v-app-bar
            app
            clipped-left
            color="#9370DB"
            dense
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-icon
              class="mx-4"
              x-large
      >
        mdi-bolnisi-cross
      </v-icon>
      <v-toolbar-title class="mr-12 align-center">
        <span class="title">PRODUCTS<b> DB - </b>ADD A NEW PRODUCT - PRODUCT TITLE -> SHOESXXXXXXXXXXXX</span>
      </v-toolbar-title>
      <v-spacer />
      <v-row
              align="center"
              style="max-width: 650px"
      >
        <v-text-field
                placeholder="Search for products..."
                append-icon="mdi-magnify"
                color="white"
                hide-details
        />

      </v-row>
    </v-app-bar>
    <v-card width="200px">
    </v-card>
    <div class="container pt-12 mt-5">
      <v-select
              :items="'Mens Clothes'"
              class="product-category"
              label="Category"
              outlined
      ></v-select>
      <v-select
              :items="'Good'"
              class="product-condition"
              label="Condition"
              outlined
      ></v-select>
      <v-select
              :items="colors"
              class="product-color"
              label="Color"
              append-icon="mdi-circle"
              outlined
      ></v-select>

      <v-select
              :items="'Clean?'"
              class="product-wash"
              label="Wash"
              outlined
      ></v-select>
      <v-select
              :items="'92% Nylon and 8% Elastane'"
              class="product-material"
              label="Material"
              outlined
      ></v-select>
      <v-select
              :items="'Machine wash cold'"
              class="product-care"
              label="Product Care"
              outlined
      ></v-select>
      <v-select
              :items="'Free People'"
              class="product-brand"
              label="Brand"
              outlined
      ></v-select>
      <v-text-field
              class="product-code"
              value="081042192"
              color="white"
              hide-details
              outlined
      />
      <v-text-field
              class="product-sku"
              placeholder="000852876156"
              color="white"
              hide-details
              outlined
      />
      <v-select
              :items="'Side slits'"
              class="product-features"
              label="Features"
              outlined
      ></v-select>
      <v-select
              :items="'Wide Sleeves'"
              class="product-accents"
              label="Accents"
              outlined
      ></v-select>
      <v-select
              :items="'Slim'"
              class="product-fit"
              label="Fit"
              outlined
      ></v-select>
      <v-select
              :items="'Casual'"
              class="product-occasion"
              label="Occasion"
              color="white"
              outlined
      />
      <v-select
              :items="seasons"
              class="product-season"
              label="Season"
              color="white"
              outlined
      />
      <v-text-field
              class="product-measurements-A"
              placeholder="Measurements (cm cm)"
              label="A"
              color="white"
              hide-details
              outlined
      />
      <v-text-field
              class="product-measurements-B"
              placeholder="Measurements (cm cm)"
              label="B"
              color="white"
              outlined
      />
      <v-text-field
              class="product-measurements-C"
              placeholder="Measurements (cm cm)"
              label="C"
              color="white"
              hide-details
              outlined
      />
      <v-text-field
              class="product-measurements-D"
              placeholder="Measurements (cm cm)"
              label="D"
              color="white"
              hide-details
              outlined
      />
      <v-select
              :items="'China'"
              class="product-country-origin"
              label="Country of origin"
              color="white"
              outlined
      />
      <v-select
              :items="'Scan106'"
              class="product-location"
              label="Location"
              color="white"
              outlined
      />
      <v-text-field
              class="product-price"
              placeholder="850€"
              label="Price"
              color="white"
              hide-details
              outlined
      />
      <v-btn outlined block class="add-continue">
        Add & Continue
      </v-btn>
      <v-btn outlined block class="add-view">
        Add & View
      </v-btn>
      <v-btn outlined block class="add-image">
        Add Image
      </v-btn>
      <v-col
              v-for="n in 9"
              :key="n"
              class="d-flex child-flex"
              cols="30"
      >
        <v-card flat tile class="d-flex">
          <v-img
                  :src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
                  :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`"
                  aspect-ratio="1"
                  class="grey lighten-2"
          >
            <template v-slot:placeholder>
              <v-row
                      class="fill-height ma-0"
                      align="center"
                      justify="center"
              >
                <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
              </v-row>
            </template>
          </v-img>
        </v-card>
      </v-col>
    </div>
  </v-app>
</template>


<style>
  /*
  .add-new-product{
    height:"200";
  }*/
  .container{
    display: grid;
    grid-template-rows: 75px 75px 75px 75px 75px 75px 75px;
    grid-template-columns: 12.5% 12.5% 12.5% 12.5% 12.5% 12.5% 12.5% 12.5% ;
    justify-items: stretch;
    align-items: stretch;
    column-gap:10px;
    justify-content: stretch;
    /*row-gap:1px;*/
  }
  .product-category{
    grid-column-start:1;
    grid-column-end:5;
    grid-row-start:1;
    grid-row-end:1;
  }
  .product-condition{
    grid-column-start:5;
    grid-column-end:9;
    grid-row-start:1;
    grid-row-end:1;
  }
  .product-color{
    grid-column-start:1;
    grid-column-end:3;
    grid-row-start:2;
    grid-row-end:2;
  }
  .product-wash{
    grid-column-start:3;
    grid-column-end:5;
    grid-row-start:2;
    grid-row-end:2;
  }
  .product-material{
    grid-column-start:5;
    grid-column-end:7;
    grid-row-start:2;
    grid-row-end:2;
  }
  .product-care{
    grid-column-start:7;
    grid-column-end:9;
    grid-row-start:2;
    grid-row-end:2;
  }
  .product-brand{
    grid-column-start:1;
    grid-column-end:3;
    grid-row-start:3;
    grid-row-end:3;
  }
  .product-code{
    grid-column-start:3;
    grid-column-end:7;
    grid-row-start:3;
    grid-row-end:3;
  }
  .product-sku{
    grid-column-start:7;
    grid-column-end:9;
    grid-row-start:3;
    grid-row-end:3;
  }
  .product-features{
    grid-column-start:1;
    grid-column-end:3;
    grid-row-start:4;
    grid-row-end:4;
  }
  .product-accents{
    grid-column-start:3;
    grid-column-end:5;
    grid-row-start:4;
    grid-row-end:4;
  }
  .product-fit{
    grid-column-start:5;
    grid-column-end:6;
    grid-row-start:4;
    grid-row-end:4;
  }
  .product-occasion{
    grid-column-start:6;
    grid-column-end:7;
    grid-row-start:4;
    grid-row-end:4;
  }
  .product-season{
    grid-column-start:7;
    grid-column-end:9;
    grid-row-start:4;
    grid-row-end:4;
  }
  .product-measurements-A{
    grid-column-start:1;
    grid-column-end:3;
    grid-row-start:5;
    grid-row-end:5;
  }
  .product-measurements-B{
    grid-column-start:3;
    grid-column-end:5;
    grid-row-start:5;
    grid-row-end:5;
  }
  .product-measurements-C{
    grid-column-start:5;
    grid-column-end:7;
    grid-row-start:5;
    grid-row-end:5;
  }
  .product-measurements-D{
    grid-column-start:7;
    grid-column-end:9;
    grid-row-start:5;
    grid-row-end:5;
  }
  .product-country-origin{
    grid-column-start:1;
    grid-column-end:4;
    grid-row-start:6;
    grid-row-end:6;
  }
  .product-location{
    grid-column-start:4;
    grid-column-end:7;
    grid-row-start:6;
    grid-row-end:6;
  }
  .product-price{
    grid-column-start:7;
    grid-column-end:9;
    grid-row-start:6;
    grid-row-end:6;
  }
  .add-continue{
    grid-column-start:1;
    grid-column-end:4;
    grid-row-start:7;
    grid-row-end:7;
  }
  .add-view{
    grid-column-start:4;
    grid-column-end:7;
    grid-row-start:7;
    grid-row-end:7;
  }
  .add-image{
    grid-column-start:7;
    grid-column-end:9;
    grid-row-start:7;
    grid-row-end:7;
  }
</style>

<script>
  export default {
    props: {
      source: String,
    },

    data: () => ({
      drawer: null,
      items: [
        { icon: 'mdi-format-list-bulleted', text: "Today's list" },
        { icon: 'mdi-cloud-download-outline', text: 'Generate eBay CSV' },
        { icon: 'mdi-cloud-download', text: 'Generate Amazon CSV' },
        { icon: 'mdi-wrench-outline', text: 'Settings' },
        { icon: 'mdi-logout', text: 'Log Out' },
      ],
      items2: [
        { text: 'Rokas Marcinkevičius' },
      ],
      seasons: [
        { text: 'Winter', value: 'Winter' },
        { text: 'Spring', value: 'Spring' },
        { text: 'Summer', value: 'Summer' },
        { text: 'Autumn', value: 'Autumn' },
      ],
      colors:[
        { icon: 'mdi-circle green', text:'Black', color: 'green'},
        { icon: 'mdi-circle green', text:'Red', color: 'green'},
        { icon: 'mdi-circle green', text:'Yellow', color: 'green'},
        { icon: 'mdi-circle green', text:'Indigo', color: 'green'},
        { icon: 'mdi-circle green', text:'Green', color: 'green'},
        { icon: 'mdi-circle green', text:'Brown', color: 'green'},

      ]
    }),
    created () {
      this.$vuetify.theme.dark = true
    },
  }
</script>