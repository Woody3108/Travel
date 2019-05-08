<template>
    <div>
        <div class="search">
            <input
                class="search-input"
                type="text"
                placeholder="请输入城市名或拼音"
                v-model="keword"
            >
        </div>
        <div class="search-content">
            <ul>
                <li>123456</li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'CitySearch',
        props: {
            cities: Object
        },
        data () {
            return {
                keword: '',
                list: [],
                timer: null
            }
        },
        // 侦听器
        watch: {
            keyword () {

            }
        }
    }
</script>

<style scoped>
    .search {
        height: .72rem;
        padding: 0 .1rem;
        background: #25a4bb;
    }

    .search-input {
        height: .62rem;
        width: 100%;
        padding: 0 .1rem;
        box-sizing: border-box;
        line-height: .62rem;
        text-align: center;
        border-radius: .06rem;
        color: #666;
    }

    .search-content {
        position: absolute;
        overflow: hidden;
        top: 1.58rem;
        left: 0;
        right: 0;
        bottom: 0;
        z-index: 1;
        background: cornflowerblue;

    }
</style>
