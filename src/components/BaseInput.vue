<template>
    <div>
        <input type="text" @change="mySearch" v-model="search">
        <button @click="mySearch">cerca</button>
    </div>
</template>

<script>
export default {
    name: 'BaseInput',
    data() {
        return {
            search: ''
        }
    },
    methods: {
        mySearch() {
            this.$emit('my-search', this.search)
        }
    }
}
</script>

<style scoped lang="scss">
</style>
