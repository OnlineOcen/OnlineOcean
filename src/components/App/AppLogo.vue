<template>
  <router-link
  class='logo'
  to='/'
  >
    <img src="@/assets/images/logo.svg" alt=""
    v-if='theme !== "dark"'
    >
    <img src="@/assets/images/logo-dark.svg" alt=""
    v-else
    >
  </router-link>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  computed: {
    ...mapGetters(['theme'])
  },
}
</script>