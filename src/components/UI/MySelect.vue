<template>
    <select :v-model="modelValue" @change="changeOtion">
      <option value="">Выберите из списка</option>
      <option v-for="option in options" :key="option.value" :value="option.value">{{ option.name }}</option>
    </select>
</template>

<script>
  export default {
    name: 'my-select',
    props: {
      modelValue: {
        type: String
      },
      options: {
        type: Array,
        default: () => []
      }
    },
    methods: {
      changeOtion(event) {
        this.$emit('update:modelValue', event.target.value)
      }
    }
  }
</script>

<style>

</style>