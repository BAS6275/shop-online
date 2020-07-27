<template>
  <v-app>
    <div>
      <v-navigation-drawer
        v-model="toggleMenu"
        width="180"
        color="orange darken-4"
        temporary
        absolute
      >
        <v-list>
          <div class="text-center">
            <v-icon large color="white">
              mdi-shield-home
            </v-icon>
          </div>
          <v-list-item
            v-for="btn in menuList"
            :key="btn.id"
            @click="toggleMenu = false"
          >
            <span class="white--text">{{ btn.name }}</span>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
      <v-app-bar color="orange darken-4" dense sticky app>
        <v-icon large color="white" class="d-none d-sm-flex">
          mdi-shield-home
        </v-icon>
        <v-app-bar-nav-icon
          class="d-flex d-sm-none"
          @click="toggleMenu = !toggleMenu"
        ></v-app-bar-nav-icon>

        <div class="d-none d-sm-flex">
          <v-btn v-for="btn in menuList" :key="btn.id" text>
            <span class="white--text">{{ btn.name }}</span>
          </v-btn>
        </div>

        <v-spacer></v-spacer>
        <v-btn icon color="white">
          <v-icon>mdi-basket</v-icon>
        </v-btn>

        <v-btn icon color="white">
          <v-icon>mdi-magnify</v-icon>
        </v-btn>

        <!-- <v-menu left bottom>
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
        </v-menu> -->
      </v-app-bar>

      <v-main>
        <nuxt />
      </v-main>

      <v-footer color="orange darken-4" padless class="d-block">
        <v-row justify="center" class="mx-12">
          <v-col
            v-for="(item, index) in footerContentList"
            :key="index"
            cols="12"
            sm="3"
            class="white--text pa-4"
            ><h4 class="pb-2">{{ item.title }}</h4>
            <div
              v-for="(i, iex) in item.detail"
              :key="iex"
              class="benefit-link"
            >
              <a>{{ i }}</a>
            </div>
          </v-col>
        </v-row>
        <div
          class="footer-color py-4 text-center white--text d-block"
          cols="12"
        >
          {{ new Date().getFullYear() }} — <strong>BasKritsanapong</strong>
        </div>
      </v-footer>
    </div>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      footerContentList: [
        {
          title: 'รวมลิงค์ที่เป็นประโยชน์',
          detail: [
            'แคตตาล็อกและโบรชัวร์',
            'แอพพลิเคชั่นเรา',
            'โปรแกรมออกแบบของเรา',
            'การรับประกันสินค้า',
            'สโตร์เราใกล้บ้านคุณ',
            'ร้านอาหารเรา',
            'มุมอาหารและขนมสวีเดน',
          ],
        },
        {
          title: 'แผนกบริการลูกค้า',
          detail: [
            'บริการของเรา',
            'นโยบายเปลี่ยนคืนสินค้า',
            'ติดตามสถานะสินค้า',
            'ติดต่อเรา',
            'คำถามที่พบบ่อย',
          ],
        },
        {
          title: 'เรื่องราวของเรา',
          detail: [
            'เกี่ยวกับเรา',
            'ทุกๆ วันที่ยั่งยืน',
            'การมีส่วนร่วมในชุมชน',
            'ดีไซน์ที่ใส่ใจทุกแง่มุม',
            'ร่วมงานกับเรา',
          ],
        },
        {
          title: 'ข่าวสาร',
          detail: [
            'ห้องข่าวประชาสัมพันธ์',
            'การยืมสินค้า',
            'ข้อมูลสื่อ',
            'สินค้าที่ถูกเรียกคืน',
            'ยึดให้แน่นหรือนำมาคืนได้',
            'คำสงวนสิทธิ์',
          ],
        },
      ],
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
          name: 'Sale',
        },
        {
          id: 2,
          name: 'สินค้ามาใหม่',
        },
        {
          id: 3,
          name: 'โปรโมชั่น',
        },
        {
          id: 4,
          name: 'อื่นๆ',
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
.footer-color {
  background-color: red;
}
</style>
