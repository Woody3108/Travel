<template>
    <div>
        <HomeHeader></HomeHeader>
    </div>
</template>

<script>
    import HomeHeader from './components/HomeHeader'

    export default {
        name: 'Home',
        components: {
            HomeHeader
        }
    }
</script>

<style scoped>
    * {
        margin: 0px;
        padding: 0px;
    }
    body {
        width: 100%;
        margin: 0px;
        padding: 0px;
    }
</style>
