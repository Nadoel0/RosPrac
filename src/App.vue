<template>
    <div class="bttns">
        <div>
            <RadioButtonText text="Кнопка переключения" />
            <RadioButtonText text="Кнопка переключения" />
            <RadioButtonText text="Кнопка переключения" :error="true"/>
            <RadioButtonText text="Кнопка переключения" :disabled="true"/>
            <RadioButtonText text="Кнопка переключения" :disabled="true" :checked="true"/>
        </div>
        <div>
            <CheckboxText text="Кнопка переключения" />
            <CheckboxText text="Кнопка переключения" />
            <CheckboxText text="Кнопка переключения" :error="true"/>
            <CheckboxText text="Кнопка переключения" :disabled="true"/>
            <CheckboxText text="Кнопка переключения" :disabled="true" :checked="true"/>
        </div>
        <div>
            <RadioButton />
            <RadioButton />
            <RadioButton :error="true"/>
            <RadioButton :disabled="true"/>
            <RadioButton :disabled="true" :checked="true"/>
        </div>
        <div>
            <Checkbox />
            <Checkbox />
            <Checkbox :error="true"/>
            <Checkbox :disabled="true"/>
            <Checkbox :disabled="true" :checked="true"/>
        </div>
    </div>
</template>

<script setup>
    import RadioButtonText from './components/buttons/RadioButtonText';
    import CheckboxText from './components/buttons/CheckboxText'
    import RadioButton from './components/buttons/RadioButton.vue';
    import Checkbox from './components/buttons/Checkbox.vue'
</script>

<style scoped>
    .bttns {
        display: flex;
        justify-content: space-between;
    }
</style>