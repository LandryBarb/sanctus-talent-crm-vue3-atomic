<template>
    <button
    :type="type"
    :class="['base-button', variantClass]"
    :disabled="disabled"
    @click="$emit('click')"
    >
    <slot></slot>

    </button>
</template>

<script setup>
const props = defineProps({
    type:{
        String,
        default: 'button', //allows use in forms too
        validator: val => ['button', 'submit', 'reset'].includes(val)
    },
    variant:{
        type: String,
        default: 'primary', // supports future: 'secondary', 'danger'
        validator: val => ['primary', 'secondary', 'danger'].includes(val)
    },
    disabled:{
        type: Boolean,
        default: false
    }
})

defineEmits(['click'])

const variantClass = `base-button--${props.variant}`
</script>

<style lang="scss">
// .base-button {
//   display: inline-flex;
//   align-items: center;
//   justify-content: center;
//   font-weight: 600;
//   padding: 0.5rem 1rem;
//   border: none;
//   border-radius: 0.5rem;
//   cursor: pointer;
//   transition: background 0.2s ease-in-out;

//   &--primary {
//     background-color: #1d3557;
//     color: #ffffff;
//   }

//   &--secondary {
//     background-color: #f1faee;
//     color: #1d3557;
//   }

//   &--danger {
//     background-color: #e63946;
//     color: #ffffff;
//   }

//   &:disabled {
//     opacity: 0.6;
//     cursor: not-allowed;
//   }
// }

</style>