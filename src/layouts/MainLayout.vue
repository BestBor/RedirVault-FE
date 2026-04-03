<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="bg-dark">
      <q-toolbar>
        <q-toolbar-title class="text-weight-bold"> RedirVault </q-toolbar-title>
        <q-btn flat color="white" to="/login" v-if="!userStore.token">Login</q-btn>
        <q-btn flat color="white" to="/register" v-if="!userStore.token" class="q-ml-sm"
          >Register</q-btn
        >
        <q-btn flat color="white" to="/" v-if="userStore.token" class="q-ml-sm">Home</q-btn>
        <q-btn flat color="red-4" @click="logout" v-if="userStore.token" class="q-ml-sm"
          >Logout</q-btn
        >
        <!-- <q-btn flat color="orange-4" to="/secured" v-if="userStore.token" class="q-ml-sm"
          >Secured</q-btn
        > -->
      </q-toolbar>
    </q-header>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { useUserStore } from '../stores/user-store'
import { useRouter } from 'vue-router'

const userStore = useUserStore()
const router = useRouter()

const logout = () => {
  userStore.logout()
  router.push('/login')
}
</script>
