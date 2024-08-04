<template>
    <div>
        <label :class="['checkbox-button', { focused, checked, disabled, error }]">
            <input 
                type="checkbox"
                :checked="checked"
                :disabled="disabled || error"
                
            />
            <span class="custom-checkbox"></span>
            <span class="checkbox-text">{{ text }}</span>
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
    .checkbox-button {
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

    .checkbox-button input {
        opacity: 0;
        position: absolute;
    }

    .custom-checkbox {
        width: 20px;
        height: 20px;
        border: solid #D5E3F0 1px;
        border-radius: 4px;
        cursor: pointer;
        background-color: #F8F9FB;
        display: inline-block;
        position: relative;
    }

    .custom-checkbox::after {
        content: "";
        position: absolute;
        display: block;
        top:  50%;
        left: 50%;
        width: 18px;
        height: 18px;
        transform: translate(-50%, -50%);
        background-image: none;
        background-color: transparent;    
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;
    }

    .checkbox-button input:checked + .custom-checkbox::after {
        background-color: transparent;
        background-image: url('data:image/svg+xml,%3Csvg width="50" height="50" viewBox="0 0 50 50" fill="none" xmlns="http://www.w3.org/2000/svg"%3E%3Cpath d="M12.5 25L20 32.5L37.5 15" stroke="%232699D4" stroke-width="10" stroke-linecap="round" stroke-linejoin="round"/%3E%3C/svg%3E');
    }

    .checkbox-button input:not(:checked):hover + .custom-checkbox::after {
        background-color: transparent;
        background-image: url('data:image/svg+xml,%3Csvg width="50" height="50" viewBox="0 0 50 50" fill="none" xmlns="http://www.w3.org/2000/svg"%3E%3Cpath d="M12.5 25L20 32.5L37.5 15" stroke="%23D5E3F0" stroke-width="10" stroke-linecap="round" stroke-linejoin="round"/%3E%3C/svg%3E');
    }

    .checkbox-button input:focus + .custom-checkbox {
        box-shadow: 0px 0px 4px 2px #0066AF99;
    }

    .checkbox-button.error .custom-checkbox {
        background-color: #FDECED;
        border: solid #EC6A71 1px;
    }

    .checkbox-button.error .checkbox-text {
        color: #EC6A71;
    }

    .checkbox-button.error input:not(:checked):hover + .custom-checkbox::after {
        background-color: initial;
        background-image: none;
    }

    .checkbox-button.disabled .custom-checkbox {
        background-color: #D5E3F0;
        border: solid #ABBCD1 1px;
    }

    .checkbox-button.disabled .checkbox-text {
        color: #ABBCD1;
    }

    .checkbox-button.disabled input:checked + .custom-checkbox::after {
        background-color: transparent;
        background-image: url('data:image/svg+xml,%3Csvg width="50" height="50" viewBox="0 0 50 50" fill="none" xmlns="http://www.w3.org/2000/svg"%3E%3Cpath d="M12.5 25L20 32.5L37.5 15" stroke="%236E7F99" stroke-width="10" stroke-linecap="round" stroke-linejoin="round"/%3E%3C/svg%3E');
    }

    .checkbox-text {
        font-family: sans-serif;
        font-size: 14px;
        line-height: 24px;
        font-weight: 100;
    }
</style>