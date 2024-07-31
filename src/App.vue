<template>
    <CheckboxText text="Текст переключателя" />
    <CheckboxText text="Текст переключателя" />
    <CheckboxText text="Текст переключателя" />
    <CheckboxText text="Текст переключателя" :error="true" />
    <CheckboxText text="Текст переключателя" :disabled="true" />
    <CheckboxText text="Текст переключателя" :disabled="true" :checked="true"/>
</template>

<script setup>
    import RadioButtonText from './components/buttons/RadioButtonText';
    import CheckboxText from './components/buttons/CheckboxText'
</script>