<template>
  <h1 class="heading-1">Tabs</h1>
  <Tabs
    :names="tabs"
    :selectedTab="selectedTab"
    @changeTab="changeTab"
  >
  <div v-if="selectedTab ==='About'">123</div>
  <div v-if="selectedTab ==='Vue'">456</div>
  <div v-if="selectedTab ==='React'">789</div>
  </Tabs>
</template>

<script setup>
import {ref} from 'vue'
  import Tabs from '@/components/Tabs.vue'

  const selectedTab = ref('Vue')
  const tabs = [
    {name: 'About', label: 'О проекте'},
    {name: 'Vue', label: 'О Vue'},
    {name: 'React', label: 'О React'},
  ]

  const changeTab = (tabName) => {
    selectedTab.value = tabName
  }
</script>
