<template>
  <section class="menu w-75">
    <button :class="{active: isListActive}" @click="$emit('toggleElement', true)">Stored Resources</button>
    <button :class="{active: !isListActive}" @click="$emit('toggleElement', false)">Add Resources</button>
  </section>
</template>

<script>
export default {
    props:{
        isListActive: {
            type: Boolean,
            required: true
        }
    },
    emits:['toggleElement']
}
</script>

<style lang="scss" scoped>
.menu {
  display: flex;
  height: 75px;
  margin-block: 2em;
  margin-inline: auto;
  border-radius: 0.5em;
  box-shadow: 0 0 10px #33333350;

  button {
    margin: 0.5em;
    padding: 0 2em;
    background: none;
    border: none;
    border-radius: 0.25em;
    color: rgb(19, 19, 100);
    font-size: 1.2rem;
  }
  .active {
    background-color: rgb(19, 19, 100);
    color: white;
  }
}
</style>
