<template>
    <div class="icons">
        <swiper class="swiper-container" >
            <swiper-slide v-for="(page, index) of pages" :key="index">
                <div class="icon"  v-for="item of page" :key="item.id">
                    <div class="icon-img">
                        <img class="icon-img-content" :src=item.imgUrl alt="">
                    </div>
                    <p class="icon-text">{{ item.text }}</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>

<script>
export default {
    name: 'HomeIcons',
    data () {
        return {
            iconList: [{
                id: '001',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                text: '景点门票字符过多点点点的效果'
            }, {
                id: '002',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                text: '景点门票'
            }, {
                id: '003',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                text: '景点门票'
            }, {
                id: '004',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                text: '景点门票'
            }, {
                id: '005',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                text: '景点门票'
            }, {
                id: '006',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                text: '景点门票'
            }, {
                id: '007',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                text: '景点门票'
            }, {
                id: '008',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                text: '景点门票'
            }, {
                id: '009',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                text: '景点门票'
            }]
        }
    },
    computed: {
        pages () {
            const pages = []
            this.iconList.forEach((item, index) => {
                const page = Math.floor(index / 8)
                if (!pages[page]) {
                    pages[page] = []
                }
                pages[page].push(item)
            })
            return pages
        }
    }
}
</script>

<style scoped>
.icons {
    overflow: hidden;
    /*height: 0;*/
    /*padding-bottom: 50%;*/
    background: darkcyan;
}
.icons >>> .swiper-container {
    height: 0;
    padding-bottom: 50%;
}
.icon {
    float: left;
    overflow: hidden;
    position: relative;
    width: 25%;
    height: 0;
    padding-bottom: 25%;
    background: #cacaca;
}
.icon-img {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: .44rem;
    box-sizing: border-box;
    padding: .1rem;
    /*background: crimson;*/
}
.icon-img-content {
    display: block;
    margin: 0 auto;
    height: 100%;
}
.icon-text {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    height: .44rem;
    line-height: .44rem;
    text-align: center;
    /* 字符过多点点点...的效果 */
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
    color: #333333;
}
</style>
