<template>
  <form class="w-75" @submit.prevent="">
    <label>Title:</label>
    <input type="text" v-model="title" />
    <label>Description:</label>
    <input type="text" v-model="description" />
    <label>Link:</label>
    <input type="text" v-model="link" />
    <BaseButton @click="sendForm" text="Add Resources" />
  </form>
  <teleport to="body">
    <InfoAlert v-if="!isValid" @close="() => (isValid = true)" />
  </teleport>
</template>

<script>
import BaseButton from './BaseButton.vue'
import InfoAlert from './InfoAlert.vue'

export default {
  props: {
    newId: Number
  },
  data() {
    return {
      title: '',
      description: '',
      link: '',
      isValid: true
    }
  },
  methods: {
    inputChecker() {
      if (this.title.length > 2 && this.description.length > 10 && this.link.length > 5) return
      else this.isValid = false
    },
    sendForm() {
      this.inputChecker()
      if (this.isValid) {
        const newSite = {
          id: this.newId,
          title: this.title,
          description: this.description,
          link: this.link
        }
        this.$emit('add-site', newSite)
      }
    }
  },
  components: { InfoAlert, BaseButton }
}
</script>
<style lang="scss" scoped>
form {
  margin-inline: auto;
  padding-left: 5%;
  padding-block: 3em;
  font-size: 0.9rem;
  box-shadow: 0 0 10px #33333346;
  label {
    font-weight: bold;
  }
  input {
    display: block;
    width: 90%;
    margin-bottom: 0.5em;
  }
}
</style>
