<template>
  <button class="button">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'my-button'
}
</script>

<style>
.button {
  padding: 5px 10px;
  background: transparent;
  border: 1px solid teal;
  border-radius: 5px;
  cursor: pointer;
}

.button:hover {
  color: #fff;
  background: teal;
  box-shadow: 0 0px 12px rgba(0,0,0,0.25), 0 1px 1px rgba(0,0,0,0.22);
}
</style>