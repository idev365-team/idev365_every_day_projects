<template>
  <div class="home">
    <div class="mysearch-search-panel">
      <MySearchLogo class="mysearch-logo"/>
      <SimpleSearchBar class="search-bar"/>
    </div>
  </div>
</template>

<script>
import MySearchLogo from '@/components/MySearchLogo.vue'
import SimpleSearchBar from '@/components/SimpleSearchBar.vue'

export default {
  name: 'home',
  components: {
    MySearchLogo,
    SimpleSearchBar
  },
}
</script>

<style lang="less" scoped>
.mysearch-search-panel{
  min-width: 840px;
  // border: solid 1px red;
}
.mysearch-logo{
  margin-top:60px;
}
.search-bar{
  margin:auto;
  margin-top:30px;
}
</style>
