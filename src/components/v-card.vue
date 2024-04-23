<template>
  <div class="v-card">
    <router-link :to="{ name: 'catalog' }">
      <div class="v-catalog_link_to_card">
        <i class="medium material-icons">shopping_basket</i>
        {{ CARD.length }}
      </div>
      <button class="btn">Back to catalog</button>
    </router-link>
    <p v-if="!CARD.length">You haven not got any products!</p>
    <vCardItem
      v-for="(item, index) in CARD"
      :key="item.article"
      v-bind:card_item_data="item"
      @deteleFromCard="deteleFromCard(index)"
    />
  </div>
</template>

<script>
import vCardItem from './v-card-item.vue'
import { mapActions, mapGetters } from 'vuex'
export default {
  name: 'v-card',
  components: {
    vCardItem
  },
  props: {
    card_data: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () { return {} },
  computed: {
    ...mapGetters(['CARD'])
  },
  methods: {
    ...mapActions(['DELETE_FROM_CARD']),
    deteleFromCard (index) {
      this.DELETE_FROM_CARD(index)
      // тут index не находится, пробовала выводить console.log(index), ничего не выводилось
    }
  }
}
</script>

<style scoped>
.v-card {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  color: grey;
  font-size: 20px;
  margin-bottom: 26px;
}
p {
  text-align: center;
  font-size: 26px;
}
</style>
