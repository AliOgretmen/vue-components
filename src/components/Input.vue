<template>
    <div>
        <input type="text" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)" />
    </div>
</template>

<script>
    export default {
        name: 'Input',
        props: {
            modelValue: String,
        },
        emits: ['update:modelValue'],
    }
</script>

<style scoped>

</style>