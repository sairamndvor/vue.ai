<template>
  <q-page class="q-pa-md">
    <div class="q-pb-md">
      <h3 class="text-h3 q-my-md">Main Dashboard</h3>
      <p class="text-subtitle1 text-grey-7">Welcome to your dashboard overview</p>
    </div>

    <!-- Tabs -->
    <q-card>
      <q-tabs
        v-model="tab"
        dense
        class="text-grey"
        active-color="primary"
        indicator-color="primary"
        align="justify"
      >
        <q-tab name="overview" icon="dashboard" label="Overview" />
        <q-tab name="graphs" icon="bar_chart" label="Graphs" />
        <q-tab name="performance" icon="speed" label="Performance" />
      </q-tabs>

      <q-separator />

      <q-tab-panels v-model="tab" animated>
        <!-- Overview Tab -->
        <q-tab-panel name="overview">
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
        </q-tab-panel>

        <!-- Graphs Tab -->
        <q-tab-panel name="graphs">
          <div class="row q-col-gutter-md">
            <div class="col-12 col-md-6">
              <q-card>
                <q-card-section>
                  <div class="text-h6">User Growth Chart</div>
                </q-card-section>
                <q-separator />
                <q-card-section class="text-center">
                  <q-icon name="show_chart" size="120px" color="primary" />
                  <div class="text-subtitle1 q-mt-md text-grey-7">Line chart showing user growth over time</div>
                  <div class="q-mt-md">
                    <q-linear-progress size="25px" :value="0.75" color="primary">
                      <div class="absolute-full flex flex-center">
                        <q-badge color="white" text-color="primary" label="75% Growth" />
                      </div>
                    </q-linear-progress>
                  </div>
                </q-card-section>
              </q-card>
            </div>

            <div class="col-12 col-md-6">
              <q-card>
                <q-card-section>
                  <div class="text-h6">Revenue Distribution</div>
                </q-card-section>
                <q-separator />
                <q-card-section class="text-center">
                  <q-icon name="pie_chart" size="120px" color="positive" />
                  <div class="text-subtitle1 q-mt-md text-grey-7">Pie chart showing revenue by category</div>
                  <div class="q-mt-md row q-gutter-sm justify-center">
                    <q-chip color="primary" text-color="white">Products 40%</q-chip>
                    <q-chip color="positive" text-color="white">Services 35%</q-chip>
                    <q-chip color="warning" text-color="white">Other 25%</q-chip>
                  </div>
                </q-card-section>
              </q-card>
            </div>

            <div class="col-12">
              <q-card>
                <q-card-section>
                  <div class="text-h6">Monthly Statistics</div>
                </q-card-section>
                <q-separator />
                <q-card-section class="text-center">
                  <q-icon name="bar_chart" size="120px" color="info" />
                  <div class="text-subtitle1 q-mt-md text-grey-7">Bar chart showing monthly performance metrics</div>
                  <div class="q-mt-md row q-col-gutter-sm">
                    <div class="col-3">
                      <q-linear-progress size="80px" :value="0.65" color="primary" vertical>
                        <div class="absolute-full flex flex-center">
                          <span class="text-white">Jan</span>
                        </div>
                      </q-linear-progress>
                    </div>
                    <div class="col-3">
                      <q-linear-progress size="80px" :value="0.80" color="positive" vertical>
                        <div class="absolute-full flex flex-center">
                          <span class="text-white">Feb</span>
                        </div>
                      </q-linear-progress>
                    </div>
                    <div class="col-3">
                      <q-linear-progress size="80px" :value="0.55" color="warning" vertical>
                        <div class="absolute-full flex flex-center">
                          <span class="text-white">Mar</span>
                        </div>
                      </q-linear-progress>
                    </div>
                    <div class="col-3">
                      <q-linear-progress size="80px" :value="0.90" color="info" vertical>
                        <div class="absolute-full flex flex-center">
                          <span class="text-white">Apr</span>
                        </div>
                      </q-linear-progress>
                    </div>
                  </div>
                </q-card-section>
              </q-card>
            </div>
          </div>
        </q-tab-panel>

        <!-- Performance Tab -->
        <q-tab-panel name="performance">
          <div class="row q-col-gutter-md">
            <div class="col-12 col-md-6">
              <q-card>
                <q-card-section>
                  <div class="text-h6">System Performance</div>
                </q-card-section>
                <q-separator />
                <q-card-section>
                  <div class="q-mb-md">
                    <div class="row items-center q-mb-sm">
                      <div class="col">CPU Usage</div>
                      <div class="col-auto text-weight-bold">45%</div>
                    </div>
                    <q-linear-progress size="20px" :value="0.45" color="positive" />
                  </div>
                  <div class="q-mb-md">
                    <div class="row items-center q-mb-sm">
                      <div class="col">Memory Usage</div>
                      <div class="col-auto text-weight-bold">62%</div>
                    </div>
                    <q-linear-progress size="20px" :value="0.62" color="warning" />
                  </div>
                  <div class="q-mb-md">
                    <div class="row items-center q-mb-sm">
                      <div class="col">Disk Usage</div>
                      <div class="col-auto text-weight-bold">38%</div>
                    </div>
                    <q-linear-progress size="20px" :value="0.38" color="primary" />
                  </div>
                  <div>
                    <div class="row items-center q-mb-sm">
                      <div class="col">Network Bandwidth</div>
                      <div class="col-auto text-weight-bold">73%</div>
                    </div>
                    <q-linear-progress size="20px" :value="0.73" color="info" />
                  </div>
                </q-card-section>
              </q-card>
            </div>

            <div class="col-12 col-md-6">
              <q-card>
                <q-card-section>
                  <div class="text-h6">Response Times</div>
                </q-card-section>
                <q-separator />
                <q-card-section>
                  <q-list>
                    <q-item>
                      <q-item-section avatar>
                        <q-icon name="api" color="positive" />
                      </q-item-section>
                      <q-item-section>
                        <q-item-label>API Response</q-item-label>
                        <q-item-label caption>Average: 45ms</q-item-label>
                      </q-item-section>
                      <q-item-section side>
                        <q-badge color="positive" label="Good" />
                      </q-item-section>
                    </q-item>
                    <q-separator />
                    <q-item>
                      <q-item-section avatar>
                        <q-icon name="storage" color="primary" />
                      </q-item-section>
                      <q-item-section>
                        <q-item-label>Database Query</q-item-label>
                        <q-item-label caption>Average: 120ms</q-item-label>
                      </q-item-section>
                      <q-item-section side>
                        <q-badge color="primary" label="Normal" />
                      </q-item-section>
                    </q-item>
                    <q-separator />
                    <q-item>
                      <q-item-section avatar>
                        <q-icon name="web" color="info" />
                      </q-item-section>
                      <q-item-section>
                        <q-item-label>Page Load</q-item-label>
                        <q-item-label caption>Average: 1.2s</q-item-label>
                      </q-item-section>
                      <q-item-section side>
                        <q-badge color="info" label="Fast" />
                      </q-item-section>
                    </q-item>
                  </q-list>
                </q-card-section>
              </q-card>
            </div>

            <div class="col-12">
              <q-card>
                <q-card-section>
                  <div class="text-h6">Performance Metrics</div>
                </q-card-section>
                <q-separator />
                <q-card-section>
                  <div class="row q-col-gutter-md">
                    <div class="col-12 col-sm-6 col-md-3">
                      <div class="text-center">
                        <q-circular-progress
                          show-value
                          font-size="12px"
                          :value="95"
                          size="100px"
                          :thickness="0.15"
                          color="positive"
                          track-color="grey-3"
                        >
                          95%
                        </q-circular-progress>
                        <div class="text-subtitle2 q-mt-sm">Uptime</div>
                      </div>
                    </div>
                    <div class="col-12 col-sm-6 col-md-3">
                      <div class="text-center">
                        <q-circular-progress
                          show-value
                          font-size="12px"
                          :value="88"
                          size="100px"
                          :thickness="0.15"
                          color="primary"
                          track-color="grey-3"
                        >
                          88%
                        </q-circular-progress>
                        <div class="text-subtitle2 q-mt-sm">Success Rate</div>
                      </div>
                    </div>
                    <div class="col-12 col-sm-6 col-md-3">
                      <div class="text-center">
                        <q-circular-progress
                          show-value
                          font-size="12px"
                          :value="76"
                          size="100px"
                          :thickness="0.15"
                          color="info"
                          track-color="grey-3"
                        >
                          76%
                        </q-circular-progress>
                        <div class="text-subtitle2 q-mt-sm">User Satisfaction</div>
                      </div>
                    </div>
                    <div class="col-12 col-sm-6 col-md-3">
                      <div class="text-center">
                        <q-circular-progress
                          show-value
                          font-size="12px"
                          :value="92"
                          size="100px"
                          :thickness="0.15"
                          color="warning"
                          track-color="grey-3"
                        >
                          92%
                        </q-circular-progress>
                        <div class="text-subtitle2 q-mt-sm">Code Quality</div>
                      </div>
                    </div>
                  </div>
                </q-card-section>
              </q-card>
            </div>
          </div>
        </q-tab-panel>
      </q-tab-panels>
    </q-card>
  </q-page>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'DashboardPage',
  setup() {
    const tab = ref('overview')
    
    return {
      tab
    }
  }
}
</script>

<style scoped>
.q-page {
  background-color: #f5f5f5;
}
</style>
