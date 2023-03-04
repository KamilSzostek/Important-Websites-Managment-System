<template>
  <div>
    <header class="p-3 bg-dark text-light text-center">
      <h1>RememberMe</h1>
    </header>
    <main>
      <Menu :isListActive="isListActive" @toggleElement="menuHandler" />
      <SiteList v-if="isListActive" :sites="sites" @site="deleteSite" />
      <AddSite v-else @add-site="addNewSite" :newId="sites[sites.length - 1].id + 1" />
    </main>
  </div>
</template>

<script>
import Menu from './components/Menu.vue'
import SiteList from './components/SiteList.vue'
import AddSite from './components/AddSite.vue'
export default {
  components: {
    Menu,
    SiteList,
    AddSite
  },
  data() {
    return {
      isListActive: true,
      sites: [
        {
          id: 1,
          title: 'Google',
          description: 'You need to know how to google!',
          link: 'https://google.pl'
        },
        {
          id: 2,
          title: 'Official Guide',
          description: 'The official Vue.js documentation.',
          link: 'https://vuejs.org/'
        }
      ]
    }
  },
  methods: {
    addNewSite(newSite) {
      this.sites.unshift(newSite)
      this.menuHandler()
    },
    deleteSite(siteId) {
      this.sites = this.sites.filter(site => site.id !== siteId)
    },
    menuHandler() {
      this.isListActive = !this.isListActive
    }
  }
}
</script>

<style lang="scss" scoped></style>
