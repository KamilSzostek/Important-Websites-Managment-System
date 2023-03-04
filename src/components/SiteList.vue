<template>
  <ul class="w-75">
    <li v-for="site in updatedSites" :key="site.id">
      <div class="d-flex">
        <h3>{{ site.title }}</h3>
        <button @click="$emit('site', site.id)">Delete</button>
      </div>
      <p>{{ site.description }}</p>
      <a :href="site.link" class="text-warning">View Resource</a>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    sites: Array
  },
  computed: {
    updatedSites() {
      return this.sites
    }
  },
  emits: ['site']
}
</script>

<style lang="scss" scoped>
ul {
  margin-inline: auto;
  list-style: none;

  li {
    padding: 1em 2em;
    margin-bottom: 3em;
    border-radius: 0.5em;
    box-shadow: 0 0 10px #3333335b;
    button {
      margin-left: auto;
      margin-right: 2em;
      background: none;
      border: none;
      color: rgb(10, 10, 100);
      font-size: 0.8rem;
      transition: color 0.5s;
      &:hover {
        color: rgb(199, 148, 38);
      }
    }
    p {
      font-size: 0.7rem;
    }
    a {
      font-size: 0.9rem;
      text-decoration: none;
    }
  }
}
</style>
