<template>
  <div class="mysearch-result-page">
    <div class="mysearch-tool-search-bar">
      <img class="mysearch-logo" src="./../assets/mysearch_logo_small.png" @click="goHome">
      <MiniSearchBar :search="searchText"/>
    </div>
    <div v-for="item in searchResultList" v-bind:key="item.id">
      <SearchResultItem :info="item"/>
    </div>
    <div class="search-no-result" v-if="searchResultList.length==0">
      没有搜索到如何内容!
    </div>
  </div>
</template>

<script>
import MiniSearchBar from '@/components/MiniSearchBar.vue'
import SearchResultItem from '@/components/SearchResultItem.vue'
import db from '@/data/search.json'

export default {
  name: 'search',
  data(){
    return {
      searchResultList:[],
    }
  },
  computed:{
    searchText(){
      console.log(this.$route)
      return this.$route.params.searchText
    },
  },
  components: {
    MiniSearchBar,
    SearchResultItem,
  },
  created(){
    this.searchResult()
  },
  beforeRouteUpdate(to, from, next){
    console.log("search page->beforeRouteUpdate:")
    next()
    this.searchResult()
  },
  methods:{
    goHome(){
      this.$router.push("/")
    },
    searchResult(){
      const searchText = this.searchText
        console.log("do searchResult",searchText)
      if(db[searchText]){
        console.log("do searchResult-->1",searchText)
        this.searchResultList = db[searchText]
      }else{
        console.log("do searchResult-->2",searchText)
        this.searchResultList = []
      }
      
    }
  }
}
</script>
<style lang="less" scoped>
@import "./../themes/base.less";
.mysearch-result-page{

}
.mysearch-tool-search-bar{
  text-align: left;
  padding:20px;
  border-bottom:solid 1px @border-color;
}
.mysearch-logo{
  width:148px;
  height:30px;
  margin-right:20px;
}
.search-no-result{
  padding:20px;
  text-align: left;
}
</style>
