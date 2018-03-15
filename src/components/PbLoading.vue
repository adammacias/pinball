<template>
  <div v-if="busy" class="pb-loading">
    <div class="d-flex justify-content-center align-items-center my-5">
      <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="25px" height="26px" class="loading">
        <image x="0px" y="0px" width="25px" height="26px" xlink:href="data:img/png;base64,iVBORw0KGgoAAAANSUhEUgAAABkAAAAaCAMAAAB1owf/AAAABGdBTUEAALGPC/xhBQAAACBjSFJNAAB6JgAAgIQAAPoAAACA6AAAdTAAAOpgAAA6mAAAF3CculE8AAAAM1BMVEWsqqqsqqqsqqqsqqqsqqqsqqqsqqqsqqqsqqqsqqqsqqqsqqqsqqqsqqqsqqqsqqr///+dko+eAAAAD3RSTlMAEbuqiO7dRCJ3VTOZZsytSHXQAAAAAWJLR0QQlbINLAAAAAd0SU1FB+IDDwoFJbN/33sAAACqSURBVCjPfVJbEgMhCAMt+Fgf979twZ1a7WIzfggxDAQBFiCCCXS9e5PxXfB6vJdDyvCeD0wOgZVxGxFppJIyWcTp+jBZU4SQnQ8Spm/JsJe5OM17EUmwRwnVnvEwOcTWHZqPW3+aknoRiTG5Do23pvwwdTQeHZVTD39xEl28docpz7s2UWfkhuOzyWWZEk1LZTMUpWhj9TXw4sntaBtbssBHJhBVsLH9xDfhtAZZ4gLS4AAAAABJRU5ErkJggg==" />
      </svg>
      <span>Page Loading</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'pb-loading',
  props: ['busy']
}
</script>

<style scoped>
.pb-loading {
  font-size: 18px;
  color: rgb(113, 113, 113);
  line-height: 1.5;
}

.pb-loading svg {
animation-name: spin;
  animation-duration: 750ms;
  animation-iteration-count: infinite;
  animation-timing-function: linear;
}

@keyframes spin {
  from {transform:rotate(0deg);}
  to {transform:rotate(360deg);}
}
</style>
