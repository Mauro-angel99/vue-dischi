<template>
    <header>
        <BaseSelect :options="genres" @change-option="emitSelectGenre" />
    </header>
</template>

<script>
import BaseSelect from './BaseSelect.vue'

export default {
    name: 'BaseHeader',
    components: {
        BaseSelect,
    },
    props: {
        genres: Array
    },
    methods: {
        emitSelectGenre(genre) {
            this.$emit('change-genre', genre)
        }
    }
}
</script>

<style lang="scss">
header {
    background-color: #2E3A46;
    height: 60px;
}
</style>