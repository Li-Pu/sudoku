<script setup lang="ts">

defineProps<{
    value?: number
}>()

</script>

<template>
    <div class="sudoku-cell">
        {{ value ?? '' }}
    </div>
</template>

<style scoped>
.sudoku-cell {
    margin: 0 auto;
    position: relative;
    top: 50%;
    transform: translateY(-50%);
}
</style>