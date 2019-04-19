<template>
    <div class="swiper">
        <swiper :options="swiperOption">
            <!-- slides -->
            <swiper-slide v-for="item of swiperList" :key="item.id">
                <img class="swiper-img" :src="item.imgUrl">
            </swiper-slide>
            <!-- Optional controls -->
            <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
        <div>hhhh</div>
    </div>
</template>

<script>
export default {
    name: 'HomeSwiper',
    data () {
        return {
            swiperOption: {
                pagination: '.swiper-pagination',
                loop: true
            },
            swiperList: [{
                id: '001',
                imgUrl: 'https://img1.qunarzz.com/vc/bf/9d/a3/67b7b37511fa26a78298bf1da1.jpg'
            }, {
                id: '002',
                imgUrl: 'https://img1.qunarzz.com/vc/80/80/1a/72b8f423c33e581ca72fc136da.jpg'
            }, {
                id: '003',
                imgUrl: 'https://img1.qunarzz.com/vc/b8/25/51/f6173dbd12c1a0f783abe73855.jpg'
            }]
        }
    },
    mounted () {
        setInterval(() => {
            console.log('simulate async data')
            if (this.swiperList.length < 3) {
                this.swiperList.push(this.swiperList.length + 1)
            }
        }, 1000)
    }
}
</script>

<style scoped>
    .swiper >>> .swiper-pagination-bullet-active {
        background: #fff;
    }
    /* 解决屏幕抖动*/
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
