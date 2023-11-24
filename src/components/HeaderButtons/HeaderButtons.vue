<template>
    <li>
        <button :class="['lg:px-7 lg:py-[10px] px-2 py-3 rounded-sm leading-tight uppercase w-full',background]">
            <slot></slot>
        </button>
    </li>
</template>

<script setup>
defineProps({
    background:{
        type: String,
        required: true
    }
})
</script>

<style lang="scss" scoped>

</style>