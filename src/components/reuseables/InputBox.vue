<template>
    <div class="input_div">
        <label v-show="label !== ''" :class="{'required' : required}">
            {{ label }}
        </label>
        <div class="text_input_container">
            <div class="eye_img_div" v-show="name === 'password'">
                <img src="/eye.png" alt="eye" class="eye_img"/>
            </div>
            <input :name="name" :value="modelValue" @input="$emit('update:modelValue', ($event.target as HTMLInputElement).value)" :placeholder="placeholder"/>
        </div>
    </div>
</template>


<script setup lang="ts">
    import { defineProps, defineEmits } from 'vue';

    defineEmits(['update:modelValue']);

    defineProps<{
        name: string,
        modelValue:string,
        label:string,
        placeholder:string,
        required:boolean
    }>()
</script>

<style>
.input_div{
    width: 100%;
    position: relative;
}
.input_div input{
    width: 100%;
    box-sizing: border-box;
    outline: none;
    padding: 20px;
    border-radius: 10px;
    border: 1px solid #DDDDDD;
    font-size: 1rem;
}

.input_div label{
    position: relative;
    display: inline-block;
    padding-bottom: 10px;
    color: #5E5E5E;
}
.input_div label.required::after{
    content: "*";
    color: red;
    display: block;
    position: absolute;
    top: 0px;
    right: -10px;
}

.text_input_container{
    position: relative;
    overflow: clip;
}
.eye_img_div{
    background-color: #F7F7F7;
    position: absolute;
    right: 0px;
    top: 0px;
    width: 60px;
    height: 100%;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 1px solid #DDDDDD;
    border-top-right-radius: 10px;
    border-bottom-right-radius: 10px;
    cursor: pointer;
}

</style>