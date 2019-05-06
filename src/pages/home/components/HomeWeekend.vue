<template>
    <div>
        <div class="title">周末去哪儿</div>
        <ul>
            <li
                class="item border-bottom"
                v-for="item of list"
                :key="item.id"
            >
                <div class="item-img-wrapper">
                    <img class="item-img" :src="item.imgUrl">
                </div>

                <div class="item-info">
                    <p class="item-title">{{ item.title }}</p>
                    <p class="item-desc">{{ item.desc }}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'HomeWeekend',
        props: {
            list: Array
        },
        data () {
            return {
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
    .item-img-wrapper {
        overflow: hidden;
        height: 0;
        padding-bottom: 37.09%;
    }
    .item-img {
        width: 100%;
    }
    .item-info {
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
        /* 字符过多点点点...的效果 */
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
        color: #333333;
    }
</style>
