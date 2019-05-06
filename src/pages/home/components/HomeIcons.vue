<template>
    <div class="icons">
        <swiper class="swiper-container" :options="swiperOption">
            <swiper-slide
                v-for="(page, index) of pages"
                :key="index"
            >
                <div
                    class="icon"
                     v-for="item of page"
                     :key="item.id"
                >
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
    props: {
        list: Array
    },
    data () {
        return {
            swiperOption: {
                autoplay: false
            }
        }
    },
    computed: {
        pages () {
            const pages = []
            this.list.forEach((item, index) => {
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
    /*background: #cacaca;*/
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
