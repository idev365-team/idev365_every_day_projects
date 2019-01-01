<template>
  <div class="search-result-toolbar">
      <img class="logo" src="./../assets/mysearch_logo_small.png" @click="goHome">
    <RoundSearchBar :search="search"/>
  </div>
</template>

<script>
import RoundSearchBar from "@/components/RoundSearchBar.vue"
export default {
    name:"search-result-toolbar",
    props:['search'],
    components:{
        RoundSearchBar
    },
    methods:{
        goHome(){
            this.$router.push("/")
        }
    }
}
</script>

<style lang="less" scoped>
@import "./../themes/base.less";
.search-result-toolbar{
    text-align: left;
    padding:@space-large;
    border-bottom: solid 1px @color-border-gray;
}
.logo{
    vertical-align: middle;
    height:@round-search-bar-height*0.8;
    margin-right:@space-large;
}
</style>
