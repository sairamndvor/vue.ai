<template>
  <q-page class="flex flex-center">
    <div class="q-pa-md text-center">
      <h2 style="color:black">Welcome to RADAR!</h2>
      
      <div class="q-gutter-md">
        <q-btn 
          label="Go to Dashboard" 
          color="primary" 
          size="lg"
          icon="dashboard"
          @click="$router.push('/dashboard')"
        />
        <q-btn 
          label="Learn More" 
          color="secondary" 
          size="lg"
          outline
          icon="info"
        />
      </div>

      <div class="q-mt-xl">
        <q-card class="q-pa-md" flat bordered>
          <q-card-section>
            <div class="text-h5 q-mb-md">Features</div>
            <div class="row q-col-gutter-md">
              <div class="col-12 col-md-4">
                <q-icon name="speed" size="48px" color="positive" />
                <div class="text-subtitle1 q-mt-sm">Fast Performance</div>
                <div class="text-caption text-grey-7">Built with Vue 3 and Vite</div>
              </div>
              <div class="col-12 col-md-4">
                <q-icon name="design_services" size="48px" color="info" />
                <div class="text-subtitle1 q-mt-sm">Modern Design</div>
                <div class="text-caption text-grey-7">Powered by Quasar Framework</div>
              </div>
              <div class="col-12 col-md-4">
                <q-icon name="devices" size="48px" color="warning" />
                <div class="text-subtitle1 q-mt-sm">Responsive</div>
                <div class="text-caption text-grey-7">Works on all devices</div>
              </div>
            </div>
          </q-card-section>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'HomePage'
}
</script>

<style scoped>
.q-page {
  min-height: 100vh;
  color: white;
}

.q-card {
  background: rgba(255, 255, 255, 0.95);
  color: #333;
}
</style>
