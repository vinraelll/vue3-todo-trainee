<template>
  <input 
    class="input"
    type="text"
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
  >
</template>

<script>
export default {
  name: 'my-input',
  props: ['modelValue'],

}
</script>

<style>
.input {
  min-width: 300px;
  margin-right: 15px;
  padding: 5px;
  border: 1px solid teal;
  border-radius: 5px;
}
</style>