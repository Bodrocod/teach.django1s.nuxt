<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="12" md="10" lg="8">
      <h1>Прайс лист</h1>
<!--      <div>-->
<!--        <v-text-field-->
<!--          v-model="search"-->
<!--          append-icon="mdi-magnify"-->
<!--          label="Поиск"-->
<!--          single-line-->
<!--          hide-details-->
<!--          class="mb-3"-->
<!--          @keyup.enter="searchProduct"-->
<!--        ></v-text-field>-->
<!--        <v-data-table-->
<!--          :headers="headers"-->
<!--          :items="products"-->
<!--          item-key="id"-->
<!--          class="elevation-1"-->
<!--          :server-items-length="count"-->
<!--          :page="currentPage"-->
<!--          :page-count="totalPages"-->
<!--          :options.sync="options"-->
<!--          :footer-props="footerProps"-->
<!--        >-->
<!--        </v-data-table>-->
<!--      </div>-->
      <div>
        <v-data-table
          :headers="headers"
          :items="products"
          item-key="name"
          class="elevation-1"
          :search="search"
          :custom-filter="filterOnlyCapsText"
          >
            <template v-slot:top>
              <v-text-field
              v-model="search"
              label="Поиск"
              class="mx-4">
              </v-text-field>
            </template>
        </v-data-table>
      </div>
    </v-col>
  </v-row>
</template>

<script>
// import {mapState, mapActions} from 'vuex'

export default {
  data() { // data() - Реквизиты формы в терминах 1С
    return {
      search: '',

      // Код для получения данных с бэка. Пока используется "заглушка", см. ниже
      // options: {},
      // footerProps: {
      //   'disable-items-per-page': true,
      //   'items-per-page-text': 'Товаров на странице',
      // }

      // "Заглушка" с данными для таблицы
      products: [
        {
          name: 'Товар 1',
          price: 100,
        },
        {
          name: 'Товар 2',
          price: 552.62,
        },
      ]
    }
  },
  computed: {
    headers() {
      return [
        {text: 'Номенклатура', value: 'name'},
        {text: 'Цена', value: 'price'},
      ]
    },
    // ...mapState({
    //   products: state => state.price.products,
    //   count: state => state.price.count,
    //   currentPage: state => state.price.currentPage,
    //   totalPages: state => state.price.totalPages,
    // }),
  },
  // watch: {
  //   options: {
  //     handler() {
  //       this.getPriceList({'page': this.options.page, 'search': undefined})
  //     },
  //   },
  //   deep: true,
  // },
  // mounted() {
  //   this.getPriceList()
  // },
  // methods: {
  //   searchProduct() {
  //     if (this.search === '') {
  //       this.getPriceList()
  //     } else {
  //       this.getPriceList({'page': undefined, 'search': this.search})
  //     }
  //   },
  //   ...mapActions({
  //     getPriceList: 'price/getPriceList'
  //   })
  // },
  methods: {
    filterOnlyCapsText(value, searh, item) {

    },
  }
}
</script>
