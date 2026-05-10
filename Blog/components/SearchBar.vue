<script setup>

defineProps({
    modelValue: String
})

const emit = defineEmits(['update:modelValue'])

</script>

<template>
    

    <label for="search">Input Search Here: </label>
    <input
        :value="modelValue"
        @input="emit('update:modelValue', $event.target.value)"
        type="text"
        placeholder="Search by title or author or tags..."
        class="search-input"
    />


</template>

<style scoped>

    .search-input {
        width: 500px;
        padding: 12px;
        margin-bottom: 30px;
        border: 1px solid #ccc;
        border-radius: 8px;
    }

    label {
        margin: 0 auto;
        font-family: 'Stack Sans Notch', sans-serif;
        font-size: 1.2em;
        margin-right: 10px;
    }

</style>
