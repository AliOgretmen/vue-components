<template>
  <h3>Component D</h3>
  <ComponentE />
</template>

<script>
import ComponentE from './ComponentE'
export default {
  name: 'ComponentD',
  components: {
    ComponentE,
  },
}
</script>

<style scoped>
</style>