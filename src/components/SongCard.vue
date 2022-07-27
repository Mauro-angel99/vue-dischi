<template>
    <div :key="author">
        <img :src="poster" alt="">
        <h4>{{ title }}</h4>
        <span>{{ author }}</span>
        <span>{{ year }}</span>
    </div>
</template>

<script>

export default {
    name: 'SongCard',
    props: {
        poster: String,
        title: String,
        author: String,
        genre: String,
        year: String
    }
}

</script>