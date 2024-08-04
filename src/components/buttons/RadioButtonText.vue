<template>
    <div>
        <label :class="['radio-button', { focused, checked, disabled, error }]">
            <input 
                type="radio"
                :checked="checked"
                :disabled="disabled || error"
                
            />
            <span class="custom-radio"></span>
            <span class="radio-text">{{ text }}</span>
        </label>
    </div>
</template>

<script setup>
    import { ref } from 'vue';

    const props = defineProps({
        text: {
            type: String,
            required: true
        },
        checked: {
            type: Boolean,
            default: false
        },
        error: {
            type: Boolean,
            default: false
        },
        disabled: {
            type: Boolean,
            default: false
        }
    });

    // const focused = ref(false);

    // const onFocus = () => {
    //     if (!props.disabled && !props.error) focused.value = true;
    // }

    // const onBlur = () => {
    //     if (!props.disabled && !props.error) focused.value = false;
    // }
</script>

<style scoped>
    .radio-button {
        display: flex;
        padding-left: 2px;
        gap: 8px;
        width: 187px;
        height: 24px;
        align-items: center;
        justify-content: center;
        text-align: center;
        position: relative;
    }

    .radio-button input {
        opacity: 0;
        position: absolute;
    }

    .custom-radio {
        width: 20px;
        height: 20px;
        border: solid #D5E3F0 1px;
        border-radius: 50%;
        cursor: pointer;
        background-color: #F8F9FB;
        display: inline-block;
        position: relative;
    }

    .custom-radio::after {
        content: "";
        position: absolute;
        display: block;
        top:  50%;
        left: 50%;
        width: 10px;
        height: 10px;
        border-radius: 50%;
        transform: translate(-50%, -50%);
    }

    .radio-button input:checked + .custom-radio::after {
        background-color: #2699D4;
    }

    .radio-button input:not(:checked):hover + .custom-radio::after {
        background-color: #D5E3F0;
    }

    .radio-button input:focus + .custom-radio {
        box-shadow: 0px 0px 4px 2px #0066AF99;
    }

    .radio-button.error .custom-radio {
        background-color: #FDECED;
        border: solid #EC6A71 1px;
    }

    .radio-button.error .radio-text {
        color: #EC6A71;
    }

    .radio-button.error input:not(:checked):hover + .custom-radio::after {
        background-color: initial;
    }

    .radio-button.disabled .custom-radio {
        background-color: #D5E3F0;
        border: solid #ABBCD1 1px;
    }

    .radio-button.disabled .radio-text {
        color: #ABBCD1;
    }

    .radio-button.disabled input:checked + .custom-radio::after {
        background-color: #6E7F99;
    }

    .radio-text {
        font-family: sans-serif;
        font-size: 14px;
        line-height: 24px;
        font-weight: 100;
    }

    .radio-text:hover {
        font-weight: 400;
    }

    .radio-button input:checked + .custom-radio + .radio-text {
        font-weight: 400;
    }
</style>