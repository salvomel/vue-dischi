<template>
    <main>
        <Select @selectClicked="searchGenre" />
        <div class="container">
            <div class="main-wrapper">

                <div v-if="!isLoadingApi" class="row row-cols-md-2 row-cols-lg-4 row-cols-xl-5">
                    <AlbumCard v-for="(album, index) in filteredAlbums" :key="index" :details="album" />
                </div>

                <Loader v-else />
            </div>
        </div>
    </main>
</template>

<script>
import axios from 'axios';
import AlbumCard from './AlbumCard';
import Select from './Select';
import Loader from './Loader';

export default {
    name: 'AlbumList',
    components: {
        AlbumCard,
        Select,
        Loader
    },
    data: function() {
        return {
            albums: [],
            selectedGenre: 'All',
            isLoadingApi: true
        };
    },
    methods: {
        searchGenre: function(select) {
            this.selectedGenre = select;
        },
    },
    computed: {
        filteredAlbums: function() {

            // Se selezionato 'All' restituisco tutto l'array di albums
            if(this.selectedGenre === 'All') {
                return this.albums;
            }

            // Altrimenti restituisco la selezione filtrata
            const filteredArray = this.albums.filter((element) => {
                return element.genre.includes(this.selectedGenre);
            });

            return filteredArray;
        }
    },
    created: function() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            this.albums = response.data.response;

            this.isLoadingApi = false;
        });
    }
}
</script>

<style scoped lang="scss">
    main {

        .main-wrapper {
            padding: 0 120px;
        }
    }
</style>