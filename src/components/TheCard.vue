<template>
    <div>
        <h4>{{ title }}</h4>
        <span>{{ originalTitle }}</span>
        <img :src="require(`../assets/${language}.png`)" alt="">
        <span>{{ vote }}</span>

    </div>
</template>

<script>

export default {
    name: 'SongCard',
    props: {
        title: String,
        originalTitle: String,
        language: String,
        vote: String
    },
}


</script>