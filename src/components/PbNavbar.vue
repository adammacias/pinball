<template>
  <nav class="pb-navbar">
    <div class="pb-navbar-header">
      <div class="container">
        <div class="d-flex align-items-center justify-content-between">
          <div class="col-logo">
            <pb-logo></pb-logo>
          </div>
          <div class="col-btn-toogle">
            <button class="btn btn-sm btn-toggle" type="button" @click="toggle()" :class="[isOpen ? 'active' : '']">
              <img src="https://s3-sa-east-1.amazonaws.com/doc88/icon-bars.svg" alt="">
            </button>
          </div>
          <div class="col-form-search col-5 d-none d-lg-block d-xl-block">
             <pb-form-search></pb-form-search>
          </div>
          <div class="col-btn-toogle-formSearch d-block d-lg-none d-xl-none">
            <button class="btn btn-sm btn-toggle" type="button" @click="toggleFormSearch()" :class="[isOpenFormSearch ? 'active' : '']">
              <img src="https://s3-sa-east-1.amazonaws.com/doc88/icon-search.svg" alt="">
            </button>
          </div>
          <div class="col-profile text-right d-none d-md-none d-lg-block">
            <img src="https://s3-sa-east-1.amazonaws.com/doc88/profile.png" alt="Photo profile" class="rounded-circle mr-2"> Welcome John
          </div>
        </div>
      </div>
    </div>
    <div class="px-4 py-3" v-if="isOpenFormSearch">
      <pb-form-search></pb-form-search>
    </div>
    <div class="pb-nav-toggle" :class="[isOpen ? 'active' : '']">
      <div class="container">
        <ul class="nav nav-pills nav-fill">
          <li class="nav-item"><a class="nav-link" href="#">My first link</a></li>
          <li class="nav-item"><a class="nav-link" href="#">Second link</a></li>
          <li class="nav-item"><a class="nav-link" href="#">Longer nav link</a></li>
          <li class="nav-item"><a class="nav-link" href="#">Link</a></li>
          <li class="nav-item"><a class="nav-link" href="#">One more link</a></li>
          <li class="nav-item"><a class="nav-link" href="#">Last link</a></li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
import PbLogo from './PbLogo.vue'
import PbFormSearch from './PbFormSearch.vue'

export default {
  name: 'pb-navbar',
  components: {
    PbLogo,
    PbFormSearch
  },
  data () {
    return {
      isOpen: false,
      isOpenFormSearch: false
    }
  },
  methods: {
    toggle: function(){
      this.isOpen = !this.isOpen
    },
    toggleFormSearch: function(){
      this.isOpenFormSearch = !this.isOpenFormSearch
    }
  }
}
</script>

<style scoped>
.pb-navbar {

  background: white;
  border-bottom: 1px solid #e7e6e5;
}

.pb-navbar .pb-navbar-header {
  padding: 1.40rem 0 1rem;
  border-bottom: 1px solid #d6d5d4;
}

/* Button Toogle */
.btn-toggle {
  border-style: solid;
  border-width: 1px;
  border-color: rgb(231, 231, 231);
  border-radius: 3px;
  background-image: -moz-linear-gradient( 90deg, rgb(245,245,245) 0%, rgb(255,255,255) 100%);
  background-image: -webkit-linear-gradient( 90deg, rgb(245,245,245) 0%, rgb(255,255,255) 100%);
  background-image: -ms-linear-gradient( 90deg, rgb(245,245,245) 0%, rgb(255,255,255) 100%);
  padding: 0
}

.btn-toggle svg {
  margin-top: -4px;
  height: 31px
}

.btn-toggle:hover {
  cursor: pointer;
}

.btn-toggle svg .icon-bar,
.btn-toggle.active svg .icon-bar {
  transition: transform .3s;
}

.btn-toggle.active svg .icon-bar:nth-of-type(1) {
  transform: translate3d(-12px,20px,0) rotate(-45deg);
}
.btn-toggle.active svg .icon-bar:nth-of-type(2) {
  opacity: 0;
}
.btn-toggle.active svg .icon-bar:nth-of-type(3) {
  transform: translate3d(17px,-8px,0) rotate(45deg);
}

/* Nav Toogle */
.pb-nav-toggle {
  overflow:hidden;
  transition:max-height 0.15s ease-out;
  height:auto;
  max-height:0;
}
.pb-nav-toggle.active {
  max-height:80px;
}

/* Nav Toogle Form Search */
.col-btn-toogle-formSearch .btn {
  position: relative;
  width: 50px;
  height: 35px
}
.col-btn-toogle-formSearch svg {
  position: absolute;
  top: 12px;
  left: 16px;
}

/*Mobile*/
@media only screen and (max-width: 768px) {
  .col-btn-toogle {
    -webkit-box-ordinal-group: 0;
    -ms-flex-order: -1;
    order: -1;
  }
}

</style>
