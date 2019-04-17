<template>
    <div class="header">
        <div class="header-left">返回</div>
        <div class="header-input"></div>
        <div class="header-right">城市</div>
    </div>
</template>

<script>
    export default {
        name: 'HomeHeader'
    }
</script>

<style scoped>
    * {
        margin: 0px;
        padding: 0px;
    }
    body {
        width: 100%;
    }
     .header {
        display: flex;
        line-height: .86rem;
        color: #ffffff;
        background: #25a4bb;
    }
    .header-left {
        width: 1.64rem;
        float: left;
    }
    .header-input {
        flex: 1;
        margin-top: .12rem ;
        margin-bottom: .12rem ;
        line-height: .64rem;
        background: #ffffff;
        border-radius: .1rem;
    }
    .header-right {
        width: 1.24rem;
        float: right;
    }
</style>
