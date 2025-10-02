<template>
  <q-page class="q-pa-md">
    <div class="q-pb-md">
      <h3 class="text-h3 q-my-md">Main Dashboard</h3>
      <p class="text-subtitle1 text-grey-7">Welcome to your dashboard overview</p>
    </div>

    <!-- Stats Cards -->
    <div class="row q-col-gutter-md q-mb-md">
      <div class="col-12 col-sm-6 col-md-3">
        <q-card>
          <q-card-section class="bg-primary text-white">
            <div class="row items-center">
              <div class="col">
                <div class="text-h6">Total Users</div>
                <div class="text-h4">1,234</div>
              </div>
              <div class="col-auto">
                <q-icon name="people" size="48px" />
              </div>
            </div>
          </q-card-section>
        </q-card>
      </div>

      <div class="col-12 col-sm-6 col-md-3">
        <q-card>
          <q-card-section class="bg-positive text-white">
            <div class="row items-center">
              <div class="col">
                <div class="text-h6">Revenue</div>
                <div class="text-h4">$45.2K</div>
              </div>
              <div class="col-auto">
                <q-icon name="attach_money" size="48px" />
              </div>
            </div>
          </q-card-section>
        </q-card>
      </div>

      <div class="col-12 col-sm-6 col-md-3">
        <q-card>
          <q-card-section class="bg-warning text-white">
            <div class="row items-center">
              <div class="col">
                <div class="text-h6">Projects</div>
                <div class="text-h4">28</div>
              </div>
              <div class="col-auto">
                <q-icon name="folder" size="48px" />
              </div>
            </div>
          </q-card-section>
        </q-card>
      </div>

      <div class="col-12 col-sm-6 col-md-3">
        <q-card>
          <q-card-section class="bg-info text-white">
            <div class="row items-center">
              <div class="col">
                <div class="text-h6">Tasks</div>
                <div class="text-h4">156</div>
              </div>
              <div class="col-auto">
                <q-icon name="assignment" size="48px" />
              </div>
            </div>
          </q-card-section>
        </q-card>
      </div>
    </div>

    <!-- Charts and Data -->
    <div class="row q-col-gutter-md">
      <div class="col-12 col-md-8">
        <q-card>
          <q-card-section>
            <div class="text-h6">Recent Activity</div>
          </q-card-section>
          <q-separator />
          <q-card-section>
            <q-list>
              <q-item v-for="i in 5" :key="i">
                <q-item-section avatar>
                  <q-avatar color="primary" text-color="white" icon="notifications" />
                </q-item-section>
                <q-item-section>
                  <q-item-label>Activity {{ i }}</q-item-label>
                  <q-item-label caption>{{ new Date().toLocaleString() }}</q-item-label>
                </q-item-section>
                <q-item-section side>
                  <q-icon name="chevron_right" />
                </q-item-section>
              </q-item>
            </q-list>
          </q-card-section>
        </q-card>
      </div>

      <div class="col-12 col-md-4">
        <q-card>
          <q-card-section>
            <div class="text-h6">Quick Actions</div>
          </q-card-section>
          <q-separator />
          <q-card-section>
            <q-btn 
              class="full-width q-mb-sm" 
              color="primary" 
              icon="add" 
              label="New Project"
            />
            <q-btn 
              class="full-width q-mb-sm" 
              color="secondary" 
              icon="person_add" 
              label="Add User"
            />
            <q-btn 
              class="full-width q-mb-sm" 
              color="positive" 
              icon="assignment" 
              label="Create Task"
            />
            <q-btn 
              class="full-width" 
              color="info" 
              icon="settings" 
              label="Settings"
            />
          </q-card-section>
        </q-card>

        <q-card class="q-mt-md">
          <q-card-section>
            <div class="text-h6">Navigation</div>
          </q-card-section>
          <q-separator />
          <q-card-section>
            <q-btn 
              class="full-width" 
              color="grey-8" 
              icon="home" 
              label="Back to Home"
              @click="$router.push('/')"
            />
          </q-card-section>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'DashboardPage'
}
</script>

<style scoped>
.q-page {
  background-color: #f5f5f5;
}
</style>
