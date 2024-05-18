<template>
  <div id="app">
    <h3>Продукты</h3>
    <ProductItem
      v-for="item in products"
      :key="item.id"
      :name="item.name"
      :price="item.price"
      :awailable="item.awailable"
      :showDescxription="item.showDescxription"
      :currencyRub="item.currencyRub"
    />
  </div>
</template>

<script>
import ProductItem from "./ProductItem.vue";

export default {
  name: "App",

  components: {
    ProductItem,
  },
  data() {
    return {
      products: [
        {
          name: "water",
          price: 120,
          awailable: true,
          showDescxription: false,
          currencyRub: true,
        },
        {
          name: "bread",
          price: 70,
          awailable: false,
          showDescxription: false,
          currencyRub: true,
        },
        {
          name: "milk",
          price: 89,
          awailable: true,
          showDescxription: false,
          currencyRub: true,
        },
        {
          name: "orange",
          price: 290,
          awailable: true,
          showDescxription: false,
          currencyRub: true,
        },
        {
          name: "butter",
          price: 170,
          awailable: true,
          showDescxription: false,
          currencyRub: true,
        },
      ],
    };
  },
  methods: {},
};
</script>
