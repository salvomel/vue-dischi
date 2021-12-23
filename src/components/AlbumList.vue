<template>
    <main>
        <div class="container">
            <div class="main-wrapper">
                <div v-if="albums.length > 0" class="row row-cols-md-2 row-cols-lg-4 row-cols-xl-5">
                    <AlbumCard v-for="(album, index) in albums" :key="index" :details="album" />
                </div>
                <Loader v-else />
            </div>
        </div>
    </main>
</template>

<script>
import axios from 'axios';
import AlbumCard from './AlbumCard';
import Loader from './Loader';

export default {
    name: 'AlbumList',
    components: {
        AlbumCard,
        Loader
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

        .main-wrapper {
            padding: 70px 120px;
        }
    }
</style>