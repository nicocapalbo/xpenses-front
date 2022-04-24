<template>
  <div>
    <p>LEDGERS</p>
    {{ user }}
  </div>
</template>

<script>
export default {
  name: 'IndexLedger',
  middleware: ['auth'],
  computed: {
    user() {
      return this.$auth.user
    }
  }
}
</script>

<style scoped>

</style>
