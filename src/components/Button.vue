<template>
  <button @click="onClick">{{ item }}</button>
</template>

<script>
export default {
  name: "Button",
  props: {
    item: String,
    onClick: Function
  }
}
</script>

<style scoped>
  button {
    border: 1px solid black;
    font-size: 16px;
    padding: 10px 15px;
    color: #2c3e50;
    background: burlywood;
    text-decoration: none;
    border-radius: 5px;
    margin: 5px;
  }

  button:hover {
    opacity: 0.9;
  }
</style>