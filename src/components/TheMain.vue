<template>
    <main>
        <section>
            <div class="container d-flex justify-content-center">
                <div class="songs">
                    <div class="song" v-for="card in cards" :key="card.poster">
                        <SongCard :poster="card.poster" :title="card.title" :author="card.author" :genre="card.genre"
                            :year="card.year" />
                    </div>
                </div>
            </div>
        </section>
    </main>
</template>

<script>
import SongCard from './SongCard.vue'
export default {
    name: 'TheMain',
    components: {
        SongCard,
    },
    props: {
        cards: Array
    }
}

</script>

<style lang="scss">
main {
    height: calc(100vh - 60px);
    background-color: #1E2D3B;
}

.songs {
    width: calc(240px * 5);
    display: flex;
    flex-wrap: wrap;
}

.song {
    width: 200px;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    background-color: #2E3A46;
    padding: 20px;
    margin: 20px;

    h4 {
        color: white;
        text-transform: uppercase;
        font-size: 18px;
    }

    span {
        color: grey;
    }
}

img {
    height: 100px;
    margin-bottom: 20px;
}
</style>