<template>
    <div class="header">
        <div class="header-left">
            <!-- 返回按钮 -->
            <div class="iconfont back-icon">&#xe624;</div>
        </div>
        <div class="header-input">
            <span class="iconfont">&#xe632;</span>
            输入城市/景点
        </div>
        <!-- 配置路由跳转到城市页 -->
        <router-link to="/city">
            <div class="header-right">
                {{ this.city}}
                <span class="iconfont arrow-icon">&#xe8ec;</span>
            </div>
        </router-link>
    </div>
</template>

<script>

    export default {
        name: 'HomeHeader',
        props: {
            city: String
        }
    }
</script>

<style scoped>
    /*在CSS中引入另一个CSS，前面要加波浪号 ~*/
    /*@import "../../../assets/styles/varibles.styl";*/
    .header {
         display: flex;
         line-height: .86rem;
         color: #ffffff;
         background: #25a4bb;
    }
    .header-left {
        width: .64rem;
        float: left;
    }
    .back-icon {
        text-align: center;
        font-size: .4rem;
    }

    .header-input {
        flex: 1;
        margin-top: .12rem;
        margin-bottom: .12rem;
        padding-left: .2rem;
        line-height: .64rem;
        color: #cccccc;
        background: #ffffff;
        border-radius: .1rem;
    }
    .header-right {
        width: 1.24rem;
        float: right;
        text-align: center;
        color: white;
    }
    .arrow-icon {
        margin-left: -.04rem;
        font-size: .24rem;
    }
</style>
