<template>
    <li class="">
        <a :href="href" :class="['no-underline', isActive ? 'border-b border-white' : '']">
            <slot></slot>
        </a>
    </li>
</template>

<script setup>
defineProps({
    href: {
        type: String,
        required: true,
      },
      isActive: Boolean,
  })
</script>

<style>

</style>