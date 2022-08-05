<template>
  <div>
    <BaseHeader :genres="genres" @change-genre="selectGenre" />
    <TheMain :cards="filterCards" />
  </div>

</template>

<script>
import axios from 'axios'
import BaseHeader from './components/BaseHeader.vue'
import TheMain from './components/TheMain.vue'



export default {
  name: 'App',
  components: {
    BaseHeader,
    TheMain,
  },
  data() {
    return {
      cards: [],
      genres: [],
      setGenre: ""
    }
  },
  mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res) => {
      this.cards = res.data.response

      this.cards.forEach(card => {
        if (!this.genres.includes(card.genre)) {
          this.genres.push(card.genre)
        }
      });
    })
  },
  computed: {
    filterCards() {
      return this.cards.filter(card => {
        if (!this.setGenre) return true
        if (card.genre === this.setGenre) return true
        else return false
      })
    }
  },
  methods: {
    selectGenre(genre) {
      this.setGenre = genre
    }
  }
}


</script>

<style lang="scss">
@import './assets/style.scss';
</style>
