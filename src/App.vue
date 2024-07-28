<template>
    <RadioButtonText text="Текст переключателя" />
    <RadioButtonText text="Текст переключателя" />
    <RadioButtonText text="Текст переключателя" />
    <RadioButtonText text="Текст переключателя" :error="true" />
    <RadioButtonText text="Текст переключателя" :disabled="true" />
    <RadioButtonText text="Текст переключателя" :disabled="true" :checked="true"/>
</template>

<script setup>
    import { ref } from 'vue';
    import RadioButtonText from './components/buttons/RadioButtonText';

    const selectedRadio = ref(false);
</script>