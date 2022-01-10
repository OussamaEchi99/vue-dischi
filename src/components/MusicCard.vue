<template>
    <a href="" class="card">
        <div class="music_image">
            <img :src="details.poster" alt="">
        </div>
        <h2>{{ details.title }}</h2>
        <div class="info">
            <span>{{ details.author }}</span>
            <span>{{ details.year }}</span>
        </div>
    </a>
</template>

<script>
export default {
    name: "musicCard",
    props: {
        details: Object
    }
}
</script>

<style lang="scss" scoped>
@import '../style/Variables.scss';

.card{
    width: calc(( 100% / 5 ) - 40px);
    background-color: $brand_primary_color;
    color: white;
    padding: 20px;
    margin: 10px 20px;
    text-align: center;

    h2{
        margin: 15px 0;
        text-transform: uppercase;
        font-size: 22px;
    }

    .info{
        color: gray;
        display: flex;
        flex-direction: column;
    }
}
</style>