<template>
<div>
    <div class="title">热销推荐</div>
    <ul>
        <li class="item border-bottom" v-for="item of list" :key="item.id">
            <img class="item-img" :src="item.imgUrl">
            <div class="item-info">
                <p class="item-title">{{ item.title }}</p>
                <p class="item-desc">{{ item.desc }}</p>
                <button class="item-button">查看详情</button>
            </div>
        </li>
    </ul>
</div>
</template>

<script>
export default {
    name: 'HomeRecommend',
    props: {
        list: Array
    },
    data () {
        return {
            // recommendList: [{
            //     id: '001',
            //     imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
            //     title: '北京故宫',
            //     desc: '故宫详细介绍故宫详细介绍故宫详细介绍故宫详细介绍故宫详细介绍故宫详细介绍'
            // }, {
            //     id: '002',
            //     imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
            //     title: '北京故宫',
            //     desc: '故宫详细介绍'
            // }, {
            //     id: '003',
            //     imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
            //     title: '北京故宫',
            //     desc: '故宫详细介绍'
            // }]
        }
    }
}
</script>

<style scoped>
    .title {
        line-height: .8rem;
        background: #eee;
        text-indent: .2rem;
    }
    .item {
        overflow: hidden;
        display: flex;
        height: 1.9rem;
        /*background: crimson;*/
    }
    .item-img {
        width: 1.7rem;
        height: 1.7rem;
        padding: .1rem;
    }
    .item-info {
        flex: 1;
        padding: .1rem;
        /* 修改点点点不显示的bug */
        min-width: 0;
    }
    .item-title {
        line-height: .54rem;
        font-size: .32rem;
        /* 字符过多点点点...的效果 */
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
        color: #333333;
    }
    .item-desc {
        line-height: .4rem;
        color: #ccc;
        /* 字符过多点点点...的效果 */
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
        color: #333333;
    }
    .item-button {
        line-height: .44rem;
        margin-top: .16rem;
        background: #ff9300;
        padding: 0 .2rem;
        border-radius: .06rem;
    }
</style>
