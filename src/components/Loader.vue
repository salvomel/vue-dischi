<template>
    <div class="loader text-center">
        <div class="fa-3x">
            <i class="fas fa-spinner fa-spin"></i>
            <div class="loading">Loading...</div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Loader"
}
</script>

<style  scoped lang="scss">
    .loader {
        color: white;

        i {
            font-size: 100px;
            margin-bottom: 30px;
        }
    }
</style>