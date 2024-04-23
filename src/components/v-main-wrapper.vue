<template>
  <div class="v-main-wrapper">
    <router-view></router-view>
    <vCatalog />
    <!-- <vCard v-if="CARD.length" :card_data="CARD" /> -->
  </div>
</template>

<script>
// import vCard from './v-card.vue'
// import vCatalog from './v-catalog.vue'
import { mapGetters } from 'vuex'
export default {
  name: 'v-main-wrapper',
  // components: { vCard, vCatalog },
  props: {},
  data () {
    return { titel: 'v-main-wrapper' }
  },
  computed: {
    ...mapGetters(['CARD'])
  },
  mounted () {},
  methods: {},
  watch: {}
}
</script>

<style>
.v-main-wrapper {
  max-width: 900px;
  margin: 0 auto;
}
</style>
