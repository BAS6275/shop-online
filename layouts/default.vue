<template>
  <v-app style="background-color: #fff;">
    <div>
      <v-navigation-drawer v-model="toggleMenu" temporary absolute>
        <v-list>
          <v-list-item
            v-for="btn in menuList"
            :key="btn.id"
            @click="toggleMenu = false"
          >
            {{ btn.name }}
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
      <v-app-bar color="orange darken-4" dense sticky app>
        <v-icon large color="white">
          mdi-shield-home
        </v-icon>
        <v-app-bar-nav-icon
          class="d-flex d-sm-none"
          @click="toggleMenu = !toggleMenu"
        ></v-app-bar-nav-icon>

        <div class="d-none d-sm-flex">
          <v-btn v-for="btn in menuList" :key="btn.id" text>{{
            btn.name
          }}</v-btn>
        </div>

        <v-spacer></v-spacer>
        <v-btn icon>
          <v-icon>mdi-basket</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>

        <v-menu left bottom>
          <template v-slot:activator="{ on, attrs }">
            <v-btn icon v-bind="attrs" v-on="on">
              <v-icon>mdi-dots-vertical</v-icon>
            </v-btn>
          </template>

          <v-list>
            <v-list-item v-for="n in 5" :key="n" @click="() => {}">
              <v-list-item-title>Option {{ n }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-app-bar>

      <v-main>
        <nuxt />
      </v-main>

      <v-footer color="orange darken-4" padless>
        <v-row justify="center" no-gutters>
          <v-col cols="12" sm="3" class="white--text benefit-link"
            ><h4>รวมลิงค์ที่เป็นประโยชน์</h4>
            <a>แคตตาล็อกและโบรชัวร์</a><br />
            <a>แอพพลิเคชั่นอิเกีย</a><br />
            <a>โปรแกรมออกแบบของอิเกีย</a><br />
            <a>การรับประกันสินค้า</a><br />
            <a>สโตร์อิเกียใกล้บ้านคุณ</a><br />
            <a>ร้านอาหารอิเกีย</a><br />
            <a>มุมอาหารและขนมสวีเดน</a><br />
            <a>IKEA Family</a><br />
            <a>IKEA Business</a><br
          /></v-col>
          <v-col cols="12" sm="3" class="white--text benefit-link"
            ><h4>รวมลิงค์ที่เป็นประโยชน์</h4>
            <a>แคตตาล็อกและโบรชัวร์</a><br />
            <a>แอพพลิเคชั่นอิเกีย</a><br />
            <a>โปรแกรมออกแบบของอิเกีย</a><br />
            <a>การรับประกันสินค้า</a><br />
            <a>สโตร์อิเกียใกล้บ้านคุณ</a><br />
            <a>ร้านอาหารอิเกีย</a><br />
            <a>มุมอาหารและขนมสวีเดน</a><br />
            <a>IKEA Family</a><br />
            <a>IKEA Business</a><br
          /></v-col>
          <v-col cols="12" sm="3" class="white--text benefit-link"
            ><h4>รวมลิงค์ที่เป็นประโยชน์</h4>
            <a>แคตตาล็อกและโบรชัวร์</a><br />
            <a>แอพพลิเคชั่นอิเกีย</a><br />
            <a>โปรแกรมออกแบบของอิเกีย</a><br />
            <a>การรับประกันสินค้า</a><br />
            <a>สโตร์อิเกียใกล้บ้านคุณ</a><br />
            <a>ร้านอาหารอิเกีย</a><br />
            <a>มุมอาหารและขนมสวีเดน</a><br />
            <a>IKEA Family</a><br />
            <a>IKEA Business</a><br
          /></v-col>
          <v-col cols="12" sm="3" class="white--text benefit-link"
            ><h4>รวมลิงค์ที่เป็นประโยชน์</h4>
            <a>แคตตาล็อกและโบรชัวร์</a><br />
            <a>แอพพลิเคชั่นอิเกีย</a><br />
            <a>โปรแกรมออกแบบของอิเกีย</a><br />
            <a>การรับประกันสินค้า</a><br />
            <a>สโตร์อิเกียใกล้บ้านคุณ</a><br />
            <a>ร้านอาหารอิเกีย</a><br />
            <a>มุมอาหารและขนมสวีเดน</a><br />
            <a>IKEA Family</a><br />
            <a>IKEA Business</a><br
          /></v-col>
          <v-col
            class="primary lighten-2 py-4 text-center white--text"
            cols="12"
          >
            {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
          </v-col>
        </v-row>
      </v-footer>
    </div>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      dropdown_font: ['Arial', 'Calibri', 'Courier', 'Verdana'],
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
      toggleMenu: false,
      menuList: [
        {
          id: 1,
          name: 'btn1',
        },
        {
          id: 2,
          name: 'btn2',
        },
        {
          id: 3,
          name: 'btn3',
        },
        {
          id: 4,
          name: 'btn4',
        },
      ],
    }
  },
}
</script>

<style>
.mr-top-2 {
  margin: 2em;
}
.bg-white {
  background-color: white;
}
.benefit-link > a {
  color: white !important;
}
</style>
