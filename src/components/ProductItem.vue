<template>
  <div class="box">
    <div class="name" @click="flagShow = !flagShow">Название:{{ name }}</div>
    <div v-if="flagShow">
      <div>Цена:{{ formattedPrice }}</div>

      <div v-if="awailable">Доступность: Awailable</div>
      <div v-else>Доступность: Out of stock</div>
      <button @click="flagCurrency = !flagCurrency">Конвертировать руб-доллары</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductItem",
  props: {
    name: String,
    price: Number,
    awailable: Boolean,
    shoshowDescxription: Boolean,
    currencyRub: Boolean,
  },
  data() {
    return {
      flagShow: this.showDescxription,
      currency: 100,
      flagCurrency: this.currencyRub,
    };
  },

  mounted() {},

  methods: {},
  computed: {
    formattedPrice() {
      if (this.flagCurrency) {
        return this.price + "руб";
      } else {
        return this.price / this.currency + "$";
      }
    },
  },
};
</script>
<style>
.box {
  display: flex;
  flex-direction: column;
  gap: 10px;
  border: solid 1px rgb(65, 55, 55);
  margin-top: 20px;
  width: 200px;
}
.name {
  cursor: pointer;
}
</style>
