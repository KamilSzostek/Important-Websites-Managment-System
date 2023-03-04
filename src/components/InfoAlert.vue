<template>
  <dialog open>
    <header>
      <h3>Invalid input</h3>
    </header>
    <main>
      <p>Unfourtunately, at leats one input value is invalid.</p>
      <p>
        Please check all inputs and make sure you enter at least a few characters into each input
        field.
      </p>
    </main>
    <footer><BaseButton text="Okay" @click="$emit('close')" /></footer>
  </dialog>
</template>

<script>
import BaseButton from './BaseButton.vue'

export default { components: { BaseButton }, emits: ['close'] }
</script>

<style lang="scss" scoped>
dialog {
  position: fixed;
  top: 50%;
  max-width: 500px;
  margin: auto;
  border-radius: 0.5em;
  box-shadow: 0 0 5px #33333367;
  transform: translateY(-50%);
  header {
    padding-block: 0.5em;
    padding-left: 1em;
    background: rgb(19, 19, 100);
    color: #fff;
  }
  main {
    padding: 1em;
    font-size: 0.9rem;
  }
  footer {
    margin-bottom: 2em;
    padding-right: 2em;
    text-align: end;
  }
}
</style>
