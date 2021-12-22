<template>
    <main>
        <div class="wrapper">
            <Album v-for="(album, index) in albums" :key="index" :albumObj="album" />
        </div>
    </main>
</template>

<script>
import Album from './Album.vue';
import axios from 'axios';

export default {
    name: 'Albumlist',
    components: {
        Album,
    },
    data: function() {
        return {
            albums: [],
        };
    },
    created: function() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            this.albums = response.data.response;
        });
    }
}
</script>

<style scoped lang="scss">
main {
    background-color: #1e2d3b;
    padding: 150px 0;
    .wrapper {
        width: 70%;
        margin: auto;
        display: flex;
        flex-wrap: wrap;
    }
}
</style>