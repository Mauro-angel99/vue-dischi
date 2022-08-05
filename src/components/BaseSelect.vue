<template>
    <select v-model="selectOption" @change="changeOption">
        <option value="">Scegli il tuo genere</option>
        <option :value="option" v-for="option in options" :key="option">{{ option }}</option>
    </select>
</template>

<script>
export default {
    name: 'BaseSelect',
    data() {
        return {
            selectOption: ""
        }
    },
    props: {
        options: Array
    },
    methods: {
        changeOption() {
            this.$emit('change-option', this.selectOption)
        }
    }
}
</script>

