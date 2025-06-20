<template>
    <span
    class="tag"
    :class="`tag--${variant}`"
    :aria-label="label"
    >
    {{ label }}
    </span>
</template>


<script setup>
defineProps({
    label:{
        type: String,
        required: true
    },
    variant: {
        type: String,
        default: 'default',
        validator: v => ['default','success', 'warning', 'error'].includes(v)
    }
})
</script>