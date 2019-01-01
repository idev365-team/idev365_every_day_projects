<template>
    <div class="home-search-bar">
        <input v-model="searchText" class="input-search" @keydown.enter="doSearch">
        <button class="btn-search" @click="doSearch">搜索一下</button>
    </div>
</template>

<script>
export default {
    name:"home-search-bar",
    data(){
        return {
            searchText:""
        }
    },
    methods:{
        doSearch(){
            if(this.searchText!==""){
                this.$router.push(`/search/${this.searchText}`)
            }
        }
    }
}
</script>

<style lang="less" scoped>
@import "./../themes/base.less";

.home-search-bar{
    max-width:650px;
}
.input-search{
    outline:none;
    width:70%;
    height:@home-search-bar-height;
    box-sizing: border-box;
    border:solid 1px #DFE1E5; 
    vertical-align: bottom;
    font-size:1.2em;
    border-top-left-radius: @home-search-bar-border-radius;
    border-bottom-left-radius: @home-search-bar-border-radius;
    padding:20px;
}
.btn-search{
    outline:none;
    width:30%;
    height:@home-search-bar-height;
    box-sizing: border-box;
    background-color: @color-primary;
    color:white;
    font-size:1.6em;
    border:none; 


    border-top-right-radius: @home-search-bar-border-radius;
    border-bottom-right-radius: @home-search-bar-border-radius;
}
</style>
