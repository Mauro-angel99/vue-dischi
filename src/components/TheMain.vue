<template>
    <main>
        <section>
            <div class="container">
                <div class="songs pt-5">
                    <div class="song" v-for="card in cards" :key="card.author">
                        <img :src="card.poster" alt="">
                        <h4>{{ card.title }}</h4>
                        <span>{{ card.author }}</span>
                        <span>{{ card.genre }}</span>
                        <span>{{ card.year }}</span>
                    </div>
                </div>
            </div>
        </section>
    </main>
</template>

<script>
import axios from 'axios'
export default {
    name: 'TheMain',
    data() {
        return {
            cards: []
        }
    },
    mounted() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res) => {
            this.cards = res.data.response
        })
    }
}

</script>

<style lang="scss">
main {
    background-color: #1E2D3B;
}

.songs {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}

.song {
    width: 18%;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    background-color: #2E3A46;
    padding: 20px;
    margin-bottom: 30px;

    h4 {
        color: white;
        text-transform: uppercase;
    }

    span {
        color: grey;
    }
}

img {
    height: 150px;
    margin-bottom: 20px;
}
</style>