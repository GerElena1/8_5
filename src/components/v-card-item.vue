<template>
  <div class="v-card-item">
    <img
      class="v-card-item_image"
      :src="require('../assets/images/' + card_item_data.image)"
      alt="pic"
    />
    <div>
      <p>{{ card_item_data.name }}</p>
      <p>{{ card_item_data.price }}</p>
      <p>{{ card_item_data.article }}</p>
      <p>{{ card_item_data.about }}</p>
    </div>
    <div class="v-card-item_quantity">
      <p>Quantity</p>
      <span> {{ card_item_data.quantity }} </span>
    </div>
    <button @click="deteleFromCard" class="btn">Delete</button>
  </div>
</template>

<script>
export default {
  name: 'v-card-item',
  props: {
    card_item_data: {
      tipe: Object,
      defauilt () {
        return {}
      }
    }
  },
  data () {
    return { titel: 'v-main-wrapper' }
  },
  computed: {},
  mounted () {},
  methods: {
    deteleFromCard () {
      this.$emit('deteleFromCard', this.card_item_data)
    }
  },
  watch: {}
}
</script>

<style lang = 'scss'>
.v-card-item {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  flex-basis: 25%;
  align-items: center;
  box-shadow: 0px 0px 8px 0px grey;
  padding: 20px;
  margin: 20px;
  &_image {
    min-width: 10%;
  }
}
</style>
