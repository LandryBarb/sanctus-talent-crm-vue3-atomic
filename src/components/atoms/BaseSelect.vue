<template>
    <div class="base-select">
        <label v-if="label" :for="id" class="base-select__label">{{ label }}</label>

        <select 
        :id="id"
        :value="modelValue"
        :disabled="disabled"
        class="base-select__field"
        @change="$emit('update:modelValue', $event.target.value)"
        >
        <options v-for="option in options" :key="option.value" :value="option.value">
            {{ option.label }}
        </options>
    </select>

    <p v-if="error" class="base-select__error" role="alert">{{ error }}</p>
    </div>
</template>




<script setup>
defineProps({
    modelValue: String,
    label: String,
    id: { type: String,
        required: true
    },
    options: { 
        type: String,
        required: true
    }, // [{ value, label }]
    error: {
        type: String,
        default: ''
    },
    disabled: {
        type: Boolean, 
        default: false
    }
})

defineEmits(['update:modelValue'])
</script>