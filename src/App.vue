<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
  </div>
</template>

<script>
import VHeader from "components/v-header/v-header.vue";
import { getSeller } from "api";
export default {
  name: "app",
  data() {
    return {
      seller: {}
    };
  },
  created() {
    this._getSeller();
  },
  methods: {
    _getSeller() {
      getSeller().then(seller => {
        console.log(seller)
        this.seller = seller;
      });
    }
  },
  components: {
    VHeader
  }
};
</script>

<style lang="stylus">
// #app
//   font-family 'Avenir', Helvetica, Arial, sans-serif
//   -webkit-font-smoothing antialiased
//   -moz-osx-font-smoothing grayscale
//   text-align center
//   color #2c3e50
//   margin-top 60px
</style>
