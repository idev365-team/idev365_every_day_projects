<template>
<div class="search-result-item">
    <a class="search-result-link" :href="info.url">
        <div class="title">{{info.title}}</div>
        <div class="url">{{info.url}}</div>
        <div class="desc">{{info.date}} - {{info.desc}}</div>
    </a>
</div>
</template>

<script>
export default {
    props:["info"]
}
</script>

<style lang="less" scoped>
.search-result-item{
    // border:solid 1px red;
    text-align: left;
    padding:20px;
}
.search-result-link{
    text-decoration: none;
}
.title{
    color:#190DAA;
    font-size: 1.25em;
}
.url{
    color:#006620;
    font-weight: bold;
}
.desc{
    color:#545454;
}
</style>
