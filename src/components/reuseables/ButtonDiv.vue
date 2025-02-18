<template>
   <div>
    <button :class="variant ? variant : 'default'">
        {{ name }}
    </button>
   </div>
</template>

<script setup lang="ts">
    import { defineProps } from 'vue';

    defineProps<{
        name: string,
        variant?:string
    }>()
</script>


<style>
.default{
    background-color: #61227D;
    color: white;
    width: 100%;
    border: none;
    padding: 20px;
    border-radius: 10px;
    font-size: 1.08em;
    font-weight: 500;
}
</style>