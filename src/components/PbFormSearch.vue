<template>
  <div class="pb-form-search">
    <form class="form-inline">
      <input class="form-control form-control-sm" type="search" placeholder="Search" aria-label="Search">
      <button class="btn btn-sm btn-outline-success" type="button">
        <img src="https://s3-sa-east-1.amazonaws.com/doc88/icon-search.svg" alt="">
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'pb-form-search'
}
</script>

<style scoped>
.pb-form-search {
  position: relative;
  width: auto;
}
.pb-form-search .form-control {
  width: 100%!important;
  background-color: rgb(247, 246, 246);
  border: 1px solid rgb(231, 231, 231);
  border-radius: 3px;
  line-height: 1.8;
}

.pb-form-search .btn {
  position: absolute;
  right: 0;
  border: 0;
  padding: .3rem .7rem .38rem;
  color: #b2b1b1;
  border-top-left-radius: 0;
  border-bottom-left-radius: 0;
  background: none;
}
</style>
