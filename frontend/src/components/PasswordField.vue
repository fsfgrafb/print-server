<script setup>
defineOptions({ inheritAttrs: false })

defineProps({
  modelValue: { type: String, default: '' },
  label: { type: String, required: true },
  autocomplete: { type: String, default: 'current-password' },
  required: { type: Boolean, default: false }
})

defineEmits(['update:modelValue'])
</script>

<template>
  <label class="password-field">
    <span>{{ label }}</span>
    <span class="password-control">
      <input
        v-bind="$attrs"
        :value="modelValue"
        type="password"
        :autocomplete="autocomplete"
        :required="required"
        @input="$emit('update:modelValue', $event.target.value)"
      />
    </span>
  </label>
</template>
