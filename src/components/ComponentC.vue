<template>
  <h2>Component C</h2>
  <ComponentD />
</template>

<script>
import ComponentD from './ComponentD'
export default {
  name: 'ComponentC',
  components: {
    ComponentD,
  },
}
</script>

<style scoped>
</style>