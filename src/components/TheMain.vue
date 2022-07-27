<template>
    <main>
        <section>
            <div class="container">
                <div class="songs pt-5">
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