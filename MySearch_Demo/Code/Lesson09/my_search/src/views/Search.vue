<template>
  <div class="search-page">
    <SearchResultToolBar v-model="search"/>
    <div v-for="info in searchResultList" :key="info.id">
      <SearchResultItem :info="info"/>
    </div>
  </div>
</template>

<script>
import SearchResultToolBar from "@/components/SearchResultToolBar.vue"
import SearchResultItem from "@/components/SearchResultItem.vue"
import RoundSearchBar from "@/components/RoundSearchBar.vue"

const DB = require("./../data/search.json")

export default {
  data(){
    console.log("this.$route",this.$route)
    return {
      searchResultList:[],
      search:this.$route.params.searchText,
    }
  },
  computed:{
  },
  created(){
    this.doSearchResult()
  },
  beforeRouteUpdate(to, from, next){
    next()
    this.doSearchResult();
  },
  methods:{
    doSearchResult(){
      const { searchText } = this.$route.params;
      if(DB.hasOwnProperty(searchText)){
        this.searchResultList = DB[searchText]
      }else{
        this.searchResultList = []
      }
      console.log("doSearchResult->",searchText,this.searchResultList)
    }
  },
  components:{
    SearchResultToolBar,
    SearchResultItem,
    RoundSearchBar,
  },
}
</script>
