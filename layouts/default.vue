<template>
  <div class="app">
    <AppHeader fixed />
    <div class="app-body">
      <Sidebar 
        :nav-items="nav" 
        fixed />
      <main class="main">
        <breadcrumb :list="list"/>
        <div class="container-fluid">
          <nuxt />
        </div>
      </main>
      <AppAside fixed/>
    </div>
    <AppFooter/>
  </div>
</template>

<script>
import nav from './menu'
import {
  Header as AppHeader,
  Sidebar,
  Aside as AppAside,
  Footer as AppFooter,
  Breadcrumb
} from '~/components/'

export default {
  name: 'Full',
  components: {
    AppHeader,
    Sidebar,
    AppAside,
    AppFooter,
    Breadcrumb
  },
  data() {
    return {
      nav: nav.items
    }
  },
  computed: {
    name() {
      return this.$route.name
    },
    list() {
      return this.$route.matched
    }
  }
}
</script>
