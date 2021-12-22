<template>
    <main>
        <div class="container">
            <div class="row row-cols-2 row-cols-lg-5">
                <AlbumCard v-for="(album, index) in albums" :key="index" :details="album" />
            </div>
        </div>
    </main>
</template>

<script>
import axios from 'axios';
import AlbumCard from './AlbumCard';

export default {
    name: 'AlbumList',
    components: {
        AlbumCard,
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
        padding: 70px;
    }
</style>