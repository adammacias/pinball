<template>
  <div id="app">
    <pb-navbar></pb-navbar>
    <div class="container pt-5" v-infinite-scroll="loadMoreArticles" infinite-scroll-disabled="busy" infinite-scroll-distance="10">
      <masonry :cols="{default: 4, 1200: 4, 992: 4, 768: 2, 576: 1}" :gutter="20">
        <div v-for="(item, index) in articles" :key="index">
          <pb-card :article="item"></pb-card>
        </div>
      </masonry>
      <pb-loading :busy="busy"></pb-loading>
    </div>
  </div>
</template>

<script>
import PbNavbar from './components/PbNavbar.vue'
import PbCard from './components/PbCard.vue'
import PbLoading from './components/PbLoading.vue'
import infiniteScroll from 'vue-infinite-scroll'
import axios from 'axios'

export default {
  name: 'app',
  components: {
    PbNavbar,
    PbCard,
    PbLoading
  },
  directives: {
    infiniteScroll
  },
  data () {
    return {
      articles: [],
      busy: false,
      search: '',
    }
  },
  methods: {
    loadMoreArticles: function() {
      this.busy = true
      var items = []
      axios.get('https://s3-sa-east-1.amazonaws.com/doc88/articles.json').then((response) => { items = response.data })

      setTimeout(() => {
        for (let i in items) {
          this.articles.push(items[i]);
        }
        this.busy = false;
      }, 1000);
    }
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Open+Sans:400,700');
@import './assets/styles/variables';
@import './assets/styles/bootstrap';
</style>
