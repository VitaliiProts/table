<template>
    <section class="y-pagination">
        <select v-model="selectedValue" @change="changeSelected(selectedValue)" class="y-pagination-select">
            <option v-for="option in ippOptions" :value="option.value">
                {{ option.value }}
            </option>
        </select>
        <button @click="onClickFirstPage" :class="[{'y-pagination-button--disabled': currentPage === 1}, 'y-pagination-button']" :disabled="currentPage === 1">
            <svg width="18" height="18" viewBox="0 0 1792 1792" xmlns="http://www.w3.org/2000/svg">
                <path d="M1011 1376q0 13-10 23l-50 50q-10 10-23 10t-23-10l-466-466q-10-10-10-23t10-23l466-466q10-10
                23-10t23 10l50 50q10 10 10 23t-10 23l-393 393 393 393q10 10 10 23zm384 0q0 13-10 23l-50 50q-10 10-23
                10t-23-10l-466-466q-10-10-10-23t10-23l466-466q10-10 23-10t23 10l50 50q10 10 10 23t-10 23l-393 393 393
                393q10 10 10 23z"/>
            </svg>
        </button>
        <button @click="currentChangePrev" :class="[{'y-pagination-button--disabled': currentPage === 1}, 'y-pagination-button']" :disabled="currentPage === 1">
            <svg width="18" height="18" viewBox="0 0 1792 1792" xmlns="http://www.w3.org/2000/svg">
                <path d="M1203 544q0 13-10 23l-393 393 393 393q10 10 10 23t-10 23l-50 50q-10 10-23
                10t-23-10l-466-466q-10-10-10-23t10-23l466-466q10-10 23-10t23 10l50 50q10 10 10 23z"/>
            </svg>
        </button>
        <section class="y-pagination-input-container">
            <span>{{ 'page' }}</span>
            <input ref="input" class="y-pagination-input" type="text" v-model="jumpPage" @keyup.enter="jumpToPage(jumpPage)"
                   @keypress="filterInput">
            <span>{{ `from ${pageCount}` }}</span>
        </section>
        <button @click="currentChangeNext" :class="[{'y-pagination-button--disabled': currentPage === pageCount}, 'y-pagination-button']" :disabled="currentPage === pageCount">
            <svg width="18" height="18" viewBox="0 0 1792 1792" xmlns="http://www.w3.org/2000/svg">
                <path d="M1171 960q0 13-10 23l-466 466q-10 10-23
                10t-23-10l-50-50q-10-10-10-23t10-23l393-393-393-393q-10-10-10-23t10-23l50-50q10-10
                23-10t23 10l466 466q10 10 10 23z"/>
            </svg>
        </button>
        <button @click="onClickLastPage" :class="[{'y-pagination-button--disabled': currentPage === pageCount}, 'y-pagination-button']" :disabled="currentPage === pageCount">
            <svg width="18" height="18" viewBox="0 0 1792 1792" xmlns="http://www.w3.org/2000/svg">
                <path d="M979 960q0 13-10 23l-466 466q-10 10-23
                10t-23-10l-50-50q-10-10-10-23t10-23l393-393-393-393q-10-10-10-23t10-23l50-50q10-10
                23-10t23 10l466 466q10 10 10 23zm384 0q0 13-10 23l-466 466q-10
                10-23 10t-23-10l-50-50q-10-10-10-23t10-23l393-393-393-393q-10-10-10-23t10-23l50-50q10-10 23-10t23
                10l466 466q10 10 10 23z"/>
            </svg>
        </button>
        <span class="y-pagination-text">{{ `Show ${currentPage} - ${pageCount} from ${total}` }}</span>
    </section>
</template>
<script src="./index.js"></script>
<style src="./index.scss" lang="scss" scoped></style>