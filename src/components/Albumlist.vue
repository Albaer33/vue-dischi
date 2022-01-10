<template>
    <main>
        <Select @optionClicked='showOption' />
        <div class="wrapper">
            <Album v-for="(album, index) in filteredAlbums" :key="index" :albumObj="album" />
        </div>
    </main>
</template>

<script>
import Album from './Album.vue';
import Select from './Select.vue';
import axios from 'axios';

export default {
    name: 'Albumlist',
    components: {
        Album,
        Select,
    },
    data: function() {
        return {
            albums: [],
            optionSelected: ''
        };
    },
    methods: {
        showOption: function(text) {
            this.optionSelected = text;
        },
    },
    computed: {
        filteredAlbums: function() {
            // se optionselected è vuoto mostra l'intero array di albums
            if(this.optionSelected === '') {
                return this.albums;
            }
            // altrimenti mostra l'array per genere
            const filteredArray = this.albums.filter((element) => {
                return element.genre.toLowerCase().includes(this.optionSelected.toLowerCase());
            });
            return filteredArray;
        }
    },
    created: function() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            this.albums = response.data.response;
        });
    },
}
</script>

<style scoped lang="scss">
main {
    background-color: #1e2d3b;
    padding: 50px 0;
    height: calc(100vh - 80px);
    .wrapper {
        width: 70%;
        margin: auto;
        display: flex;
        flex-wrap: wrap;
    }
}
</style>