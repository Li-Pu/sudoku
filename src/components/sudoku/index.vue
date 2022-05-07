<script setup lang="ts">
import sudokuCell from './cell.vue';

</script>

<template>
    <div class="sudoku-wrapper">
        <div class="sudoku-container">
            <div class="sudoku-row" v-for="rowIndex in 9" :key="rowIndex">
                <div class="sudoku-column" v-for="colomnIndex in 9" :key="rowIndex + '-' + colomnIndex">
                    <sudoku-cell :value="Math.floor(Math.random() * 9 + 1)" />
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.sudoku-wrapper {
    position: relative;
    width: 80%;
    left: 10%;
    top: 10%;
    padding-bottom: 80%;
}

.sudoku-container {
    position: absolute;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    display: flex;
    flex-direction: column;
    align-items: stretch;
    justify-content: space-between;
    border: 3px solid grey;
}

.sudoku-row {
    flex: 1;
    display: flex;
    align-items: stretch;
    justify-content: space-between;
    flex-direction: row;
}

.sudoku-column {
    flex: 1;
    justify-content: space-between;
    flex-direction: row;
    border: 1px solid grey;
    border-left-width: 0px;
    border-top-width: 0px;
}

.sudoku-row:nth-of-type(3) .sudoku-column,
.sudoku-row:nth-of-type(6) .sudoku-column {
    border-bottom-width: 2px;
}

.sudoku-column:nth-of-type(3),
.sudoku-column:nth-of-type(6) {
    border-right-width: 2px;
}

.sudoku-row:nth-of-type(9) .sudoku-column {
    border-bottom-width: 0px;
}

.sudoku-column:nth-of-type(9) {
    border-right-width: 0px;
}
</style>