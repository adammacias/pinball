<template>
  <div class="pb-social-sharing">
    <a :href="facebookLinkFake" target="_blank" class="btn-social rounded-circle">
      <img src="https://s3-sa-east-1.amazonaws.com/doc88/icon-facebook.svg" alt="" class="icon-facebook">
    </a>
  </div>
</template>

<script>
export default {
  name: 'pb-social-sharing',
  data () {
    return {
      facebookLinkFake: "https://www.facebook.com/sharer/sharer.php?u=https%3A%2F%2Fdevelopers.facebook.com%2Fdocs%2Fsharing%2Fweb%2F&amp;display=popup&amp;ref=plugin&amp;src=like&amp;kid_directed_site=0&amp;app_id=113869198637480"
    }
  }
}
</script>

<style scoped>
.pb-social-sharing .btn-social {
  position: relative;
  padding: 1px 11px;
  background: rgb(214, 214, 214);
}

.pb-social-sharing .btn-social:hover {
  background: rgb(59,89,152);
}

.pb-social-sharing .btn-social .icon-facebook {
  position: absolute;
  top: 6px;
  left: 5px;
}
</style>
