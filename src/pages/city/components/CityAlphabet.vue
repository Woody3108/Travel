<template>
    <ul class="list">
        <li
            class="item"
            v-for="item of letters"
            :key="item"
            :ref="item"
            @click="handleLetterClick"
            @touchstart="handleTouchStart"
            @touchmove="handleTouchMove"
            @touchend="handleTouchEnd"
        >
            {{ item }}
        </li>
    </ul>
</template>

<script>
    export default {
        name: 'CityAlphabet',
        props: {
            cities: Object
        },
        data () {
          return {
              touchStatus: false
          }
        },
        computed: {
            letters () {
                let letters = []
                for (let i in this.cities) {
                    letters.push(i)
                }
                return letters
            }
        },
        methods: {
            handleLetterClick (e) {
                const log = console.log.bind(console)
                log('当前点击字母', e.target.innerText)
                // 子组件 CityAlphabet 传值给父组件 City.vue
                this.$emit('change', e.target.innerText)
            },
            handleTouchStart (e) {
                this.touchStatus = true
            },
            handleTouchMove (e) {
                if (this.touchStatus) {
                    // offsetTop 拿到元素距顶端的高度
                    let startY = this.$refs['A'][0].offsetTop
                    let touchY = e.touches[0].clientY - 79
                    let index = Math.floor((touchY - startY) / 20)
                    console.log('startY', startY)
                    console.log('touchY', touchY)
                    console.log('index', index)
                    let l = this.letters
                    if (index >= 0 && index <= l.length) {
                        this.$emit('change', l[index])
                    }
                }
            },
            handleTouchEnd () {
                this.touchStatus = false
            }
        }
    }
</script>

<style scoped>
    .list {
        display: flex;
        flex-direction: column;
        justify-content: center;
        position: absolute;
        top: 1.58rem;
        right: 0;
        bottom: 0;
        width: .4rem;
        /*background: red;*/
    }
    .item {
        line-height: .4rem;
        text-align: center;
        color: #25a4bb;
    }
</style>
