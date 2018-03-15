<template>
  <div class="pb-star-rating">
    <span class="rating-star" v-for="(item, index) in countStar" :key="index" :class="[stars > index ? 'rating-star-active' : '']"></span>
  </div>
</template>

<script>
export default {
  name: 'pb-star-rating',
  props: ['stars'],
  data () {
    return {
      countStar: 4
    }
  }
}
</script>

<style scoped>
.pb-star-rating .rating-star:before {
  content: '\2605';
  font-size: 1.45rem;
  line-height: 0.5rem;
  color: #dddddd;
}

.pb-star-rating .rating-star.rating-star-active:before {
  color: #bacc45;
}
</style>
