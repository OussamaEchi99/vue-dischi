<template>
    <main>
        <div class="container">
            <div class="select_menu">
                <SelectTypeMusic @searchDone="searchTypeClicked" />
            </div>
            <div class="discs">
                <MusicCard v-for="(card, index) in filteredTypeMusic()" :key="index" :details="card" />
            </div>
        </div>
    </main>
</template>

<script>
import axios from 'axios';

import SelectTypeMusic from "./SelectTypeMusic.vue";
import MusicCard from "./MusicCard.vue";


export default {
    name: "App",
    components: {
        MusicCard,
        SelectTypeMusic
    },
    data: function () {
        return {
            musicCards: [],
            typeClicked: '',
        };
    },
    methods: {
        musicCardsAPI: function () {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((response) => {
                this.musicCards = response.data.response;
            });
        },
        searchTypeClicked: function (text) {
            this.typeClicked = text
            console.log(this.typeClicked);
        },
        filteredTypeMusic: function () {
            if (this.typeClicked === '') {
                return this.musicCards
            }

            const filteredArray = this.musicCards.filter((element) => {
                return element.genre.includes(this.typeClicked);
            });

            return filteredArray
        }
    },
    created: function () {
        this.musicCardsAPI()
    }
}
</script>

<style lang="scss" scoped>
@import '../style/Variables.scss';

main{
    background-color: $brand_secondary_color;
    height: calc(100vh - 70px);

    .container{

        .select_menu{
            padding: 20px 0;
        }

        .discs{
            padding-top: 10px;
            display: flex;
            flex-wrap: wrap;
        }
    }
}
</style>