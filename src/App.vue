<template>
  <div>
    <BaseHeader />
    <TheMain :cards="this.cards" />
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
@import './assets/style.scss';
</style>
