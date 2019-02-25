<template>
    <div class="round-search-bar">
        <input :value="value" @input="doInputChange" class="input-search" @keydown.enter="doSearch">
        <button class="btn-search" @click="doSearch">
            <img class="icon-search" src="./../assets/icon_search.svg">
        </button>
    </div>
</template>

<script>
import Util from "@/common/Util"
export default {
    name:"round-search-bar",
    props:{
        value:String,
    },
    methods:{
        doInputChange(event){
            this.$emit('change',event.target.value)
        },
        doSearch(){
            console.log(this)
            Util.searchAPI(this.$router,this.search)
        }
    }
}
</script>

<style lang="less" scoped>
@import "./../themes/base.less";

.round-search-bar{
    width:400px;
    position: relative;
    display: inline-block;
}
.input-search{
    outline: none;
    width:100%;
    height:@round-search-bar-height;
    border-radius:@round-search-bar-border-radius;
    border:solid 1px @color-border-gray;
    padding:20px;
    box-sizing: border-box;
    font-size: 1.2em;
}
.btn-search{
    outline: none;
    height:@round-search-bar-height;
    position: absolute;
    right:0;
    top:50%;
    transform: translateY(-50%);
    background: none;
    border:none;
}
.icon-search{
   width:30px;
   height:30px;
   margin-right:15px;

}
</style>

