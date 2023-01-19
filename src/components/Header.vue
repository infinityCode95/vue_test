<template>
    <header class="header">
        <h4 class="title">{{ title }}</h4>
    </header>
</template>

<script>
export default {
    name: 'Header',
    data: () => ({
        title: 'Ты сегодня покормил кота?'
    }),    
}
</script>

<style lang="scss" scoped>
.title {
    font-family: 'Exo 2', sans-serif;
    font-size: 36px;
    line-height: 44px;
    text-align: center;
    text-shadow: 0px 1px 1px #000000;
    font-weight: 200;
    margin: 0px 0px 24px 0px;
    color: #FFFFFF;
}
</style>