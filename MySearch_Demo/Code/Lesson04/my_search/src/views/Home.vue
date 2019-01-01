<template>
  <div class="home">
    <MySearchLogo class="my-search-logo"/>
  </div>
</template>

<script>
// @ is an alias to /src
import MySearchLogo from '@/components/MySearchLogo.vue'

export default {
  name: 'home',
  components: {
    MySearchLogo
  }
}
</script>

<style lang="less" scoped>
.my-search-logo{
  margin-top: 60px;
}
</style>

