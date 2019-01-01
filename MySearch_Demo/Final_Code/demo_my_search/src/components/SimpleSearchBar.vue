<template>
    <div class="sample-search-bar">
       <input v-focus v-model="searchText" class="input-search" @keydown.enter="search">
       <button class="btn-search" @click="search">搜索一下</button>
    </div>
</template>

<script>
import Util from '@/common/util'

export default {
    data(){
        return {
            searchText:"",
        }
    },
    mounted(){
        this.$nextTick(function () {
            console.log(this)
        })
    },
    methods:{
        search(){
            Util.searchAPI(this.$router,this.searchText)
        }
    },
    directives: {
        focus: {
            // 指令的定义
            inserted: function (el) {
                el.focus()
            }
        }
    }
}
</script>


<style lang="less" scoped>
@import "./../themes/base.less";
.sample-search-bar{
    width:800px;
}
.input-search{
    outline:none;
    width:60%;
    height:@simple-search-bar-height;
    border:solid 1px @border-color;
    box-sizing: border-box;
    vertical-align: bottom;
    font-size:1.2em;
    padding:10px;
    border-top-left-radius: @simple-search-bar-radius;
    border-bottom-left-radius: @simple-search-bar-radius;
}
.btn-search{
    outline:none;
    width:20%;
    height:@simple-search-bar-height;
    background-color:@color-primary;
    color:white;
    border:solid 1px @color-primary;
    font-size:1.2em;
    font-weight: bold;
    border-top-right-radius: @simple-search-bar-radius;
    border-bottom-right-radius: @simple-search-bar-radius;
}
</style>
