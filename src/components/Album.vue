<template>
    <div class="album">
        <div class="album-img">
            <img :src="albumObj.poster" :alt="albumObj.author">
        </div>
        <div class="album-text">
            <div class="title">{{albumObj.title}}</div>
            <div class="author">{{albumObj.author}}</div>
            <div class="year">{{albumObj.year}}</div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Album',
    props: {
        albumObj: Object
    }
}
</script>

<style scoped lang="scss">
.album {
    width: calc((100% / 5) - 40px);
    margin: 10px 20px;
    background-color: #2e3a46;
    &-img {
        padding: 20px;
    }
    &-text {
        text-align: center;
        padding-bottom: 10px;
        .title {
            font-size: 22px;
            padding: 3px;
            color: white;
        }
        .author, .year {
            padding: 2px;
            color: #717375;
        }
    }
}
</style>