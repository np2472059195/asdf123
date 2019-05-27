<template>
    <header>
        <i class="iconfont icon-return"></i>
        <input type="text" placeholder="请输入商品名">
        <i class="iconfont icon-collection"></i>
        <i class="iconfont icon-more"></i>
    </header>
</template>

<script>
export default {

}
</script>

<style scoped>
    header{
            height: 50px;
            width: 100%;
            background:red;
            line-height: 50px;
            display: flex;
        }
        i{
            font-size:30px;
            padding: 0 10px 0 5px;
        }
        input{
            flex:1;
            height: 40px;
            margin-top: 5px;
            border-radius:20px;
            border:2px solid #ccc;
            text-indent:20px;
        }
</style>