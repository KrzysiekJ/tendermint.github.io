<template>
<!-- This file is automatically generated from `./build/templates` -->
<div class="master" v-bind:class="{ 'mobile-active': isActive, 'mobile-inactive': !isActive }" @click="toggleManual">
  <nav>
  <div class="title">Index</div>
  <router-link :to="'/intro'" exact>Introduction</router-link>
  <router-link :to="'/intro/tendermint-vs-x'">1. Tendermint vs X</router-link>
  <router-link :to="'/intro/abci-overview'">2. ABCI Overview</router-link>
  <router-link :to="'/intro/consensus-overview'">3. Consensus Overview</router-link>
  <div class="title">Getting Started</div>
  <router-link :to="'/intro/getting-started/download-tendermint'">1. Download Tendermint</router-link>
  <router-link :to="'/intro/getting-started/first-app'">2. First App</router-link>
  <router-link :to="'/intro/getting-started/deploy-testnet'">3. Deploy Testnet</router-link>
  <router-link :to="'/intro/getting-started/next-steps'">4. Next Steps</router-link>
</nav>
  <btn-thumb v-show="isActive" icon="close"></btn-thumb>
  <btn-thumb v-show="!isActive" icon="bars"></btn-thumb>
</div><!--master-->
</template>

<script>
import $ from 'jquery'
import BtnThumb from './BtnThumb'

export default {
  name: 'page-docs-master',
  components: {
    BtnThumb
  },
  data () {
    return {
      isActive: false
    }
  },
  methods: {
    toggleAutomatic () {
      let self = this
      if ($(window).width() >= 768) self.isActive = true
      else self.isActive = false
    },
    toggleManual () {
      if ($(window).width() < 768) {
        this.isActive = !this.isActive
      }
    }
  },
  mounted () {
    this.toggleAutomatic()
    $(window).resize(() => this.toggleAutomatic())
  }
}
</script>
