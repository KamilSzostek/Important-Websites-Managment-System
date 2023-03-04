<template>
  <button>{{ text }}</button>
</template>

<script>
export default {
    props:{
        text: String
    }
}
</script>

<style lang="scss" scoped>
button {
  margin-top: 1em;
  padding: 0.25em 0.5em;
  background-color: rgb(19, 19, 100);
  border: 2px solid transparent;
  border-radius: 0.25em;
  color: #fff;
  font-size: 1rem;
  transition: 0.5s;
  &:hover {
    background-color: #fff;
    color: rgb(19, 19, 100);
    border: 2px solid rgb(19, 19, 100);
  }
}
</style>
