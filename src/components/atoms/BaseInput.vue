<template>
  <div class="base-input">
    <label v-if="label" :for="id" class="base-input__label">
      {{ label }}
    </label>

    <input
      :id="id"
      :type="type"
      :value="modelValue"
      :placeholder="placeholder"
      :disabled="disabled"
      aria-describedby="description ? `${id}-desc` : undefined"
      :aria-invalid="error ? 'true' : 'false'"
      class="base-input__field"
      @input="$emit('update:modelValue', $event.target.value)"
    />
    <p v-if="description" :id="`${id}-desc`" class="base-input__description">
      {{ description }}
    </p>
    <p v-if="error" class="base-input__error" role="alert">
      {{ error }}
    </p>
  </div>
</template>

<script setup>
defineProps({
    modelValue: {
        type: String,
        default: ''
    },
    label: {
        type:String,
        default: ''
    },
    id: {
        type: String,
        required: true
    },
    type: {
        type: String,
        default: 'text'
    },
    placeholder: {
        type: String,
        default: ''
    },
    description: {
        type: String,
        default: ''
    },
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
