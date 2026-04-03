<template>
  <q-page padding>
    <div class="row justify-center">
      <div class="col-12 col-md-8 col-lg-6">
        <AddLink class="q-mb-xl" />
        <CardLink v-for="link in useLink.links" :key="link._id" :link="link" />
      </div>
    </div>
  </q-page>
</template>

<script setup>
import { useLinkStore } from '../stores/link-store'

// Components
import AddLink from 'src/components/AddLink.vue'
import CardLink from 'src/components/CardLink.vue'

const useLink = useLinkStore()
// useLink.getLinks()
</script>
