<template>
  <app-header></app-header>
  <div class="header-gap"></div>
  <router-view/>
  <app-footer></app-footer>

  {{ live }}

</template>

<script>
import AppHeader from '@/components/App/AppHeader.vue'
import AppFooter from '@/components/App/AppFooter.vue'

import axios from 'axios';

export default {
  components:{
    AppHeader, 
    AppFooter,
  },

  data() {
    return {
      live: null,
    }
  },  
  mounted () {
    this.getData()
  },
  methods: {
    getData() {
      axios.get('https://api.nftgeek.app/api/1/collectionFeed?order=after&sequenceId=82042465294872&timeMillis=1650485855556')
        .then(function (response) {
          // handle success
          console.log(response);
          this.live = response
        })
        .catch(function (error) {
          // handle error
          console.log(error);
        })
        // .then(function () {

        // });
    }
  },
}
</script>

<style lang="scss">
@import './assets/style/main.scss';
</style>