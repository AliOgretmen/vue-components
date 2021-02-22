<template>
  <h4>Component E</h4>
  <h3>Component E username - {{ userName }}</h3>
</template>

<script>
export default {
  name: 'ComponentE',
  inject: ['userName'],
}
</script>

<style scoped>
</style>