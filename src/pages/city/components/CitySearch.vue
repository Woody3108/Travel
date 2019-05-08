<template>
    <div>
        <div class="search">
            <input
                class="search-input"
                type="text"
                placeholder="请输入城市名或拼音"
                v-model="keyword"
            >
        </div>
        <div class="search-content">
            <ul>
                <li
                    v-for="item of list"
                    :key="item.id"
                >
                    {{ item.name }}
                </li>
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
                keyword: '',
                list: [],
                timer: null
            }
        },
        // 侦听器
        watch: {
            keyword () {
                const log = console.log.bind(console)
                if (this.timer) {
                    clearTimeout(this.timer)
                }
                if (!this.keyword) {
                    this.list = []
                    return
                }
                this.timer = setTimeout(() => {
                    const result = []
                    for (let i in this.cities) {
                        this.cities[i].forEach((value) => {
                            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
                                result.push(value)
                                log('this.keyword', this.keyword)
                                log('搜索的结果--->', value)
                            }
                        })
                    }
                    this.list = result
                }, 100)
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
