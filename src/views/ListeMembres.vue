<script setup>
import { useMembresStore } from '@/stores/membres'

// const membresStore = inject('membres');
const membresStore = useMembresStore();

</script>

<template>
  <main>
    <h2 class="title">Liste des membres</h2>
    <ul>
     
        <li class="box" v-for="membre in membresStore.state.membres">
          <router-link :to="{ name: 'membre', params: { id: membre.id } }">
            <h2 class="title is-3">{{ membre.fullname }}</h2>
            <p class="subtitle">{{ membre.email }}</p>
          </router-link>
        </li>
    </ul>
  </main>
</template>