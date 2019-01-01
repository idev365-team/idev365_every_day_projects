<template>
    <div class="sample-search-bar">
       <input v-model="searchText" class="input-search" @keydown.enter="doSearch">
       <button class="btn-search" @click="doSearch">
           <img class="icon-search" src="./../assets/icon_search.svg">
       </button>
    </div>
</template>
<script>
import Util from '@/common/util'

export default {
    props:["search"],
    data(){
        return {
            searchText:this.search
        }
    },
    methods:{
        doSearch(){
            console.log("mini search doSearch")
            Util.searchAPI(this.$router,this.searchText)
        }
    }
}
</script>

<style lang="less" scoped>
@import "./../themes/base.less";
.sample-search-bar{
    width:500px;
    // border: 1px red solid;
    position: relative;
    display: inline-block
}
.input-search{
    outline:none;
    width:100%;
    height:@mini-search-bar-height;
    border:solid 1px @border-color;
    box-sizing: border-box;
    vertical-align: bottom;
    font-size:1.2em;
    padding:20px 20px;
    border-radius: @mini-search-bar-height/2;
}
.btn-search{
    outline:none;
    width:60px;
    height:@mini-search-bar-height;
    right:0;
    position: absolute;
    background: transparent;
    border:none;
}
.icon-search{
    width:20px;
    height:20px;
}
</style>
