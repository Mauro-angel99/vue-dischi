<template>
  <div>
    <BaseHeader />
    <TheMain />
  </div>

</template>

<script>
import BaseHeader from './components/BaseHeader.vue'
import TheMain from './components/TheMain.vue'




export default {
  name: 'App',
  components: {
    BaseHeader,
    TheMain,
  }
}
</script>

<style lang="scss">
@import './assets/style.scss';
</style>
