<template>
  <v-app>
    <!-- Sidebar -->
    <v-navigation-drawer app v-model="drawer" :clipped="$vuetify.display.mdAndUp">
      <v-list>
        <v-list-item title="Dashboard" prepend-icon="mdi-view-dashboard" />
        <v-list-item title="Reports" prepend-icon="mdi-chart-line" />
        <v-list-item title="Settings" prepend-icon="mdi-cog" />
      </v-list>
    </v-navigation-drawer>

    <!-- Top App Bar -->
    <v-app-bar app color="primary" dark>
      <v-app-bar-nav-icon @click="drawer = !drawer" />
      <v-toolbar-title>My Dashboard</v-toolbar-title>
    </v-app-bar>

    <!-- Main Content -->
    <v-main>
      <v-container fluid>
        <v-row>
          <v-col cols="12" md="4">
            <v-card class="pa-4">
              <v-card-title>Total Users</v-card-title>
              <v-card-text class="text-h5 font-weight-bold">1,240</v-card-text>
            </v-card>
          </v-col>
          <v-col cols="12" md="4">
            <v-card class="pa-4">
              <v-card-title>Revenue</v-card-title>
              <v-card-text class="text-h5 font-weight-bold">$8,430</v-card-text>
            </v-card>
          </v-col>
          <v-col cols="12" md="4">
            <v-card class="pa-4">
              <v-card-title>Active Projects</v-card-title>
              <v-card-text class="text-h5 font-weight-bold">27</v-card-text>
            </v-card>
          </v-col>
        </v-row>

        <!-- Data Table -->
        <v-row>
          <v-col cols="12">
            <v-card>
              <v-card-title>User List</v-card-title>
              <v-data-table
                :headers="headers"
                :items="users"
                class="elevation-1"
              ></v-data-table>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'

const drawer = ref(true)

const headers = [
  { title: 'Name', value: 'name' },
  { title: 'Email', value: 'email' },
  { title: 'Role', value: 'role' }
]

const users = [
  { name: 'Alice Johnson', email: 'alice@example.com', role: 'Admin' },
  { name: 'Bob Smith', email: 'bob@example.com', role: 'Editor' },
  { name: 'Carol Lee', email: 'carol@example.com', role: 'Viewer' }
]
</script>

<style scoped>
.v-card {
  border-radius: 16px;
}
</style>


<script>
import { defineComponent } from 'vue';

// Components
import HelloWorld from '../components/HelloWorld.vue';

export default defineComponent({
  name: 'HomeView',

  components: {
    HelloWorld,
  },
});
</script>
