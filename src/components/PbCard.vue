<template>
  <div class="pb-card mb-3">
    <div class="card">
      <div class="card-img-wrap clearfix">
        <img class="card-img-top" :src="article.cover" alt="Card image cap">
      </div>
      <div class="card-body">
        <h5 class="card-title" v-text="article.title"></h5>
        <p class="card-text card-text-local">
          <img src="https://s3-sa-east-1.amazonaws.com/doc88/icon-local.svg" alt="" class="mr-1">
          {{ article.local }}
        </p>
        <p class="card-text card-text-excerpt" v-html="article.excerpt"></p>
      </div>
      <div class="card-footer d-flex justify-content-between">
        <pb-star-rating :stars="article.stars"></pb-star-rating>
        <pb-social-sharing></pb-social-sharing>
      </div>
    </div>
  </div>
</template>

<script>
import PbStarRating from './PbStarRating.vue'
import PbSocialSharing from './PbSocialSharing.vue'

export default {
  name: 'pb-card',
  components: {
    PbStarRating,
    PbSocialSharing
  },
  props: ['article']
}
</script>

<style scoped>
.card {
  border: 0;
  box-shadow: 0px 0px 4px 1px rgba(0,0,0,0.12);
}

.card-body {
  padding: .85rem 1.25rem;
}

.card-footer {
  background: rgba(255,255,255,1);
}

.card-title {
  font-size: 18px;
  color: rgb(113, 113, 113);
  line-height: 1.5;
  margin-bottom: .2rem;
}

.card-text-local {
  font-size: 14px;
  color: rgb(172, 170, 170);
  margin-bottom: 1rem;
}

.card-text-excerpt {
  font-size: 13px;
  color: rgb(172, 170, 170);
  line-height: 1.23;
}

.card-img-wrap {
  overflow: hidden;
  position: relative;
}

.card-img-wrap:after {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  background: rgba(255,255,255,0.3);
  opacity: 0;
  transition: opacity .25s;
}
.card-img-wrap img {
  transition: transform .25s;
  width: 100%;
}
.card:hover .card-img-wrap img {
  transform: scale(1.2);
}
.card:hover .card-img-wrap:after {
  opacity: 1;
}

.card:hover {
  cursor: pointer;
}
</style>
