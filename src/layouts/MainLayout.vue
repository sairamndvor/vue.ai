<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="bg-primary text-white">
      <q-toolbar>
        <q-toolbar-title>
          RADAR Application
        </q-toolbar-title>
        <q-btn flat round dense icon="menu" class="q-mr-sm">
          <q-menu>
            <q-list style="min-width: 100px">
              <q-item clickable v-close-popup @click="$router.push('/')">
                <q-item-section>
                  <q-icon name="home" class="q-mr-sm" />
                  Home
                </q-item-section>
              </q-item>
              <q-item clickable v-close-popup @click="$router.push('/dashboard')">
                <q-item-section>
                  <q-icon name="dashboard" class="q-mr-sm" />
                  Dashboard
                </q-item-section>
              </q-item>
            </q-list>
          </q-menu>
        </q-btn>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer elevated class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <div class="text-center">© 2025 RADAR</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
export default {
  name: 'MainLayout'
}
</script>
