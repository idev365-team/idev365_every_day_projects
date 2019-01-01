<template>
    <div class="search-result-item">
        <a :href="info.url" class="title">{{ info.title }}</a>
        <a :href="info.url" class="url">{{ info.url }}</a>
        <div>
            <a :href="info.url" class="desc">{{info.date}} - {{ info.desc }}</a>
        </div>
    </div>
</template>

<script>
export default {
    props:["info"]
}
</script>

<style lang="less" scoped>
@import "./../themes/base.less";

.search-result-item{
    // border:solid 1px red;
    text-align: left;
    padding:20px;
}

.title{
    color:#190DAA;
    font-size: 1.2em;
    text-decoration: none;
}
.url{
    color:#006620;
    font-size: 0.8em;
    font-weight: bold;
    text-decoration: none;
}
.desc{
    color:#545454;
    font-size: 0.9em;
    text-decoration: none;
}
</style>


