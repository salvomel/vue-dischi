<template>
    <div class="col mb-4">
        <div class="card h-100 text-center">
            <img :src="details.poster" class="card-img-top" alt="details.title">
            <div class="card-body">
                <h5 class="card-title">{{details.title}}</h5>
                <div class="card-text">{{details.author}}</div>
                <div class="card-year">{{details.year}}</div>
            </div>
        </div>
  </div>
</template>

<script>
export default {
    name: 'AlbumCard',
    props: {
        details: Object
    }
}
</script>

<style scoped lang="scss">
@import '../style/variables';

    .card {
        background-color: $secondary-color;
        padding: 20px;

        .card-body {
            color: $sub-text-color;

            .card-title {
                text-transform: uppercase;
                color: $text-color;
                font-weight: bold;
                font-size: 18px;
            }

            .card-text {
                font-size: 17px;
                margin-top: 20px;
            }
        }  
    }
</style>