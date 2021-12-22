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

</style>