<template>
    <div class="logo_header">
        <img src="../assets/img/Spotify_logo_without_text.svg" alt="">
    </div>
</template>

<script>
export default {
    
}
</script>

<style lang="scss" scoped>
@import '../style/Variables.scss';

.logo_header{
    height: 70px;
    background-color: $brand_primary_color;
    display: flex;
    align-content: center;

    img{
        width: 2%;
        margin: 0 20px;
    }
}
</style>