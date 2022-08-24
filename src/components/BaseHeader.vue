<template>
  <header>
    <BaseInput @my-search="emitSearch" />
  </header>
</template>

<script>
import BaseInput from './BaseInput.vue'
export default {
  name: 'BaseHeader',
  components: {
    BaseInput,
  },
  methods: {
    emitSearch(search) {
      this.$emit('my-search', search)
    }
  }
}
</script>

<style scoped lang="scss">
</style>
