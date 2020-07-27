<template>
  <div>
    <div max-width="auto" class="mr-top-2">
      <v-carousel height="300" show-arrows-on-hover cycle>
        <v-carousel-item
          v-for="(item, i) in imgItems"
          :key="i"
          :src="item.src"
          reverse-transition="fade-transition"
          transition="fade-transition"
        ></v-carousel-item>
      </v-carousel>
    </div>

    <!-- Product image -->
    <v-row class="d-flex flex-wrap mr-top-2 justify-center">
      <v-col
        v-for="(item, index) in productList"
        :key="index"
        cols="12"
        sm="4"
        md="3"
      >
        <v-hover v-slot:default="{ hover }">
          <v-card :elevation="hover ? 16 : 2" class="mr-top-2">
            <!-- มีปัญหา -->
            <v-img class="setPosition" :src="item.src"></v-img>

            <v-card-title>{{ item.productName }}</v-card-title>
            <v-card-text>
              <div>
                {{ item.price }}
              </div>
              <v-row align="center" class="mx-0">
                <v-rating
                  :value="4.5"
                  color="amber"
                  dense
                  half-increments
                  readonly
                  size="14"
                ></v-rating>

                <div class="dark--text ml-4">4.5 (413)</div>
              </v-row>

              <div>
                {{ item.detail }}
              </div>
            </v-card-text>

            <v-divider class="mx-4"></v-divider>

            <v-card-actions>
              <v-btn color="deep-purple lighten-2" text>
                หยิบเข้าตระกร้า
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-hover>
      </v-col>
    </v-row>

    <!-- end of picture  -->
    <div class="text-center">
      <v-btn
        class="ma-2"
        tile
        outlined
        color="success"
        @click="seeMoreHandler()"
        >สินค้าเพิ่มเติม</v-btn
      >
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      page: 1,
      items: [
        {
          id: 1,
          productName: 'chair',
          detail: 'รายละเอียดสินค้า',
          price: '100$',
          src:
            'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQSPAYBDq_ogHF22hywk1jNI_TS_EgpYhMA6w&usqp=CAU',
        },
        {
          id: 2,
          productName: 'chair2',
          detail: 'รายละเอียดสินค้า2',
          price: '250$',
          src: 'https://www.mangosiam.com/images/slide/2.jpg',
        },
        {
          id: 3,
          productName: 'chair3',
          price: '350$',
          detail: 'รายละเอียดสินค้า3',
        },
        {
          id: 4,
          productName: 'chair4',
          price: '150$',
          detail: 'รายละเอียดสินค้า3',
        },
        {
          id: 5,
          productName: 'chair5',
          price: '400$',
          detail: 'รายละเอียดสินค้า3',
        },
        {
          id: 6,
          productName: 'chair6',
          price: '65$',
          detail: 'รายละเอียดสินค้า3',
        },
        {
          id: 7,
          productName: 'chair7',
          price: '350$',
          detail: 'รายละเอียดสินค้า3',
        },
        {
          id: 8,
          productName: 'chair8',
          detail: 'รายละเอียดสินค้า3',
          price: '350$',
        },
        {
          id: 9,
          productName: 'chair8',
          detail: 'รายละเอียดสินค้า3',
          price: '350$',
        },
        {
          id: 10,
          productName: 'chair8',
          detail: 'รายละเอียดสินค้า3',
        },
        {
          id: 11,
          productName: 'chair8',
          detail: 'รายละเอียดสินค้า3',
        },
        {
          id: 12,
          productName: 'chair8',
          detail: 'รายละเอียดสินค้า3',
        },
        {
          id: 13,
          productName: 'chair8',
          detail: 'รายละเอียดสินค้า3',
        },
        {
          id: 14,
          productName: 'chair8',
          detail: 'รายละเอียดสินค้า3',
        },
        {
          id: 15,
          productName: 'chair15',
          detail: 'รายละเอียดสินค้า3',
        },
        {
          id: 16,
          productName: 'chair16',
          detail: 'รายละเอียดสินค้า3',
        },
        {
          id: 17,
          productName: 'chair16',
          detail: 'รายละเอียดสินค้า3',
        },
        {
          id: 18,
          productName: 'chair18',
          detail: 'รายละเอียดสินค้า3',
        },
      ],
      imgItems: [
        {
          src:
            'https://family.ikea.co.th/storage/sale-preview/2020-JUL/sale-page-banner-th.jpg',
        },
        {
          src:
            'https://www.whatphone.net/wp-content/uploads/2019/05/promotion-banana-tme-2019-may.jpg',
        },
        {
          src:
            'https://d2rmw7fiarhdss.cloudfront.net/media//saleandpromotion/category/New-normal-promotion-page-1000x495.png',
        },
        {
          src:
            'https://www.sansiri.com/singlehouse/kanasiri-wongwaen-lamlukka/img/Coverbanner/kanasiri-wongwaen-lamlukka-house-cover-banner-desktop-1920x800-02.jpg?v=1.0.1',
        },
      ],
      productList: [],
      productLength: 8,
    }
  },
  created() {
    this.productList = this.items.slice(0, this.productLength)
  },
  methods: {
    seeMoreHandler() {
      this.productList = this.items.slice(
        0,
        this.productLength + this.productList.length
      )
    },
  },
}
</script>
//CSS stye
<style>
.bg-white {
  background-color: white;
}
.mr-top-2 {
  margin: 20px;
}

.mr-top-banner {
  margin-top: 5px;
}

.setPosition {
  max-width: 100%;
  height: auto !important;
}
</style>
