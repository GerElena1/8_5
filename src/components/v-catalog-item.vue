<template>
  <div class="v-catalog-item">
    <img
      class="v-catalog-item_image"
      :src="require('../assets/images/' + product_data.image)"
      alt="pic"
    />
    <p class="v-catalog-item_name">{{ product_data.name }}</p>
    <p class="v-catalog-item_price">{{ product_data.price }}</p>
    <button class="v-catalog-item_add_to_card_btn btn" @click="addToCard">
      Add to card
    </button>
  </div>
</template>

<script>
export default {
  name: 'v-catalog-item',
  props: {
    product_data: {
      tipe: Object,
      defauilt () {
        return {}
      }
    }
  },
  data () { return {} },
  methods: {
    addToCard () {
      this.$emit('addToCard', this.product_data)
    }
  }
}
</script>

<style lang="scss">
.v-catalog-item {
  flex-basis: 40%;
  box-shadow: 0px 0px 8px 0px grey;
  padding: 20px;
  margin: 20px;
  &_img {
    width: 160px;
    display: block;
    margin: 0 auto;
  }
}
</style>
