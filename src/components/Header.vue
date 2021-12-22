<template>
    <header>
        <img src="../assets/logo-small.svg" alt="Logo Spotify">
    </header>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style scoped lang="scss">
@import '../style/variables';

header {
    background-color: $secondary-color;
    
   img {
       height: 50px;
       padding: 10px 20px;
   }
}
</style>