<template>
  <div>
      {{name}} {{lastName}}
  </div>
</template>

<script>
  export default {
    name: 'Greet',
    props: ['name', 'lastName']
  }
</script>

<style>

</style>
