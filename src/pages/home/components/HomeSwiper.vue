<template>
    <div class="swiper">
        <swiper
            :options="swiperOption"
            v-if="showSwiper"
        >
            <!-- slides -->
            <swiper-slide
                v-for="item of list"
                :key="item.id"
            >
                <img class="swiper-img" :src="item.imgUrl">
            </swiper-slide>
            <!-- Optional controls -->
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>
<script>
    export default {
        name: 'HomeSwiper',
        props: {
            list: Array
        },
        data () {
            return {
                swiperOption: {
                    pagination: '.swiper-pagination',
                    loop: true
                }
            }
        },
        computed: {
            // 解决首次进入页面时候，list为空就开始渲染数据
            // 让真正的数据加载后再开始渲染 swiper
            showSwiper () {
                return this.list.length
            }
        },
        mounted () {
            setInterval(() => {
                // console.log('simulate async data')
                if (this.list.length < 3) {
                    this.list.push(this.list.length + 1)
                }
            }, 1000)
        }
    }
</script>

<style scoped>
    .swiper >>> .swiper-pagination-bullet-active {
        background: #fff;
    }

    /* 解决屏幕抖动 */
    .swiper {
        width: 100%;
        height: 0;
        overflow: hidden;
        padding-bottom: 31.25%;
        background: #cacaca;
    }

    .swiper-img {
        width: 100%;
    }

</style>
