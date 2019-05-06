<template>
    <ul class="list">
        <li
            class="item"
            v-for="(item, key) of cities"
            :key="key"
            @click="handleLetterClick"
            @touchstart="handleTouchStart"
            @touchmove="handleTouchMove"
            @touchend="handleTouchEnd"
        >
            {{ key }}
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
        methods: {
            handleLetterClick (e) {
                const log = console.log.bind(console)
                log('当前点击字母', e.target.innerText)
                // 子组件 CityAlphabet 传值给父组件 City.vue
                this.$emit('change', e.target.innerText)
            },
            handleTouchStart () {

            },
            handleTouchMove () {

            },
            handleTouchEnd () {

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
    }
    .item {
        line-height: .4rem;
        text-align: center;
        color: #25a4bb;
    }
</style>
