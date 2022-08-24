<template>
    <main>
        <div>
            <h1>FILM</h1>
            <div v-for="movie in movies" :key="movie.poster">
                <TheCard :title="movie.title" :originalTitle="movie.original_title" :language="movie.original_language"
                    :vote="movie.vote_average" />
            </div>
        </div>
        <div>
            <h1>SERIE TV</h1>
            <div v-for="tvShow in tvShows" :key="tvShow.id">
                <TheCard :title="tvShow.name" :originalTitle="tvShow.original_name" :language="tvShow.original_language"
                    :vote="tvShow.vote_average" />
            </div>
        </div>
    </main>
</template>

<script>
import TheCard from './TheCard.vue'
export default {
    name: 'TheMain',
    components: {
        TheCard,
    },
    props: {
        movies: Array,
        tvShows: Array
    }
}
</script>

<style scoped lang="scss">
</style>
