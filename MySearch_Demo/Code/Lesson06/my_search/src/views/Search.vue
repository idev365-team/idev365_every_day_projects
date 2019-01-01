<template>
  <div class="search-page">
    <SearchResultToolBar :search="search"/>
  </div>
</template>

<script>
import SearchResultToolBar from "@/components/SearchResultToolBar.vue"
export default {
  components:{
    SearchResultToolBar
  },
  computed:{
    search(){
      return this.$route.params.searchText
    }
  }
}
</script>
