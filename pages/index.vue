<template>
  <div>
    <div max-width="auto" class="mr-top-2">
      <v-carousel height="300" show-arrows-on-hover cycle hide-delimiters>
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
            <v-img :src="item.src" contain aspect-ratio="1.5"></v-img>

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
                เลือกชุดนี้
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-hover>
      </v-col>
    </v-row>

    <!-- end of picture  -->
    <div class="text-center">
      <v-btn
        class="ma-5"
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
          productName: 'ชุดห้อง',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          price: '100$',
          src:
            'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQSPAYBDq_ogHF22hywk1jNI_TS_EgpYhMA6w&usqp=CAU',
        },
        {
          id: 2,
          productName: 'ชุดห้อง2',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          price: '250$',
          src: 'https://www.mangosiam.com/images/slide/2.jpg',
        },
        {
          id: 3,
          productName: 'ชุดห้อง3',
          price: '350$',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          src: 'https://www.mangosiam.com/images/slide/2.jpg',
        },
        {
          id: 4,
          productName: 'ชุดห้อง4',
          price: '150$',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          src:
            'https://sbmedia3.sbdesignsquare.com/output/images/gallery/50779/f7f61a845c5c8dad2f13334dea918118.jpg',
        },
        {
          id: 5,
          productName: 'ชุดห้อง5',
          price: '400$',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          src:
            'https://yusabuy.com/wp-content/uploads/2019/02/Koncept-Furniture-%E0%B8%A0%E0%B8%B2%E0%B8%9E%E0%B8%97%E0%B8%B5%E0%B9%88-18.jpg',
        },
        {
          id: 6,
          productName: 'ชุดห้อง6',
          price: '65$',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          src:
            'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSXW-KrbwuGfP08oGw1OhsVDBNF4UM-zAAWYA&usqp=CAU',
        },
        {
          id: 7,
          productName: 'ชุดห้อง7',
          price: '350$',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          src:
            'https://www.dooddot.com/wp-content/uploads/2017/09/1-Baker-JLD_Roomscene-16.jpg',
        },
        {
          id: 8,
          productName: 'ชุดห้อง8',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          price: '350$',
          src:
            'https://i.pinimg.com/originals/b4/4d/0c/b44d0cbf1357e529416e7718ba7d1cc8.jpg',
        },
        {
          id: 9,
          productName: 'ชุดห้อง9',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          price: '350$',
          src: 'https://www.mangosiam.com/images/slide/2.jpg',
        },
        {
          id: 10,
          productName: 'ชุดห้อง10',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          price: '350$',
          src: 'https://www.mangosiam.com/images/slide/2.jpg',
        },
        {
          id: 11,
          productName: 'ชุดห้อง11',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          price: '350$',
          src: 'https://www.mangosiam.com/images/slide/2.jpg',
        },
        {
          id: 12,
          productName: 'ชุดห้อง12',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          price: '350$',
          src: 'https://www.mangosiam.com/images/slide/2.jpg',
        },
        {
          id: 13,
          productName: 'ชุดห้อง13',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          price: '350$',
          src: 'https://www.mangosiam.com/images/slide/2.jpg',
        },
        {
          id: 14,
          productName: 'ชุดห้อง14',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          price: '350$',
          src: 'https://www.mangosiam.com/images/slide/2.jpg',
        },
        {
          id: 15,
          productName: 'ชุดห้อง15',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          price: '350$',
          src: 'https://www.mangosiam.com/images/slide/2.jpg',
        },
        {
          id: 16,
          productName: 'ชุดห้อง16',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          price: '350$',
          src: 'https://www.mangosiam.com/images/slide/2.jpg',
        },
        {
          id: 17,
          productName: 'ชุดห้อง17',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          price: '350$',
          src: 'https://www.mangosiam.com/images/slide/2.jpg',
        },
        {
          id: 18,
          productName: 'ชุดห้อง18',
          detail: 'ประกอบด้วย เตียง ที่วางของหัวเตียง',
          price: '350$',
          src: 'https://www.mangosiam.com/images/slide/2.jpg',
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
</style>
