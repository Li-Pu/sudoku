<script setup lang="ts">
import { onMounted, ref } from 'vue';
import Sudoku from '../../components/sudoku/index.vue';

const { clientWidth, clientHeight } = document.documentElement;
const width = ref(Math.min(clientWidth, clientHeight));

onMounted(() => {
    window.addEventListener('resize', () => {
        const { clientWidth, clientHeight } = document.documentElement;
        width.value = Math.min(clientWidth, clientHeight);
    })
})
</script>

<template>
    <div :style="{ width: width + 'px', height: width + 'px' }">
        <Sudoku data="data" />
    </div>
</template>