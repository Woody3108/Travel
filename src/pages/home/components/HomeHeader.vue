<template>
    <div class="header">
        <div class="header-left">返回</div>
        <div class="header-input">输入城市/景点</div>
        <div class="header-right">城市</div>
    </div>
</template>

<script>
    export default {
        name: 'HomeHeader'
    }
</script>

<style scoped>
    .header {
         display: flex;
         line-height: .86rem;
         color: #ffffff;
         background: #25a4bb;
         text-align: center;
    }

    .header-left {
        width: .64rem;
        float: left;
    }

    .header-input {
        flex: 1;
        margin-top: .12rem;
        margin-bottom: .12rem;
        line-height: .64rem;
        color: #cccccc;
        background: #ffffff;
        border-radius: .1rem;
    }

    .header-right {
        width: 1.24rem;
        float: right;
        /*text-align: center;*/
    }
</style>
