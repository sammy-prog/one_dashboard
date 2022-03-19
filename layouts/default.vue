<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      app
      dark
      disable-resize-watcher
      color="#2C2D40"
    >
      <img class="mt-4 ml-5" style="cursor:pointer" height="37" width="144" src="/onestreamlogo.png" alt="onestream_logo" />
      <div class="line"></div>
      <v-list class="mb-16">
        <v-list-item class="mt-2" to="/">
          <v-list-item-action>
            <v-icon>mdi-apps</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Dashboard</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item class="mt-2" to="/Accounts">
          <v-list-item-action>
            <v-icon>mdi-account-outline</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Accounts</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="mt-3 line"></div>

        <p class="mt-4 ml-5">OneStream Storage</p>
        <v-list-item class="mt-2" to="/Videos">
          <v-list-item-action>
            <v-icon>mdi-movie-roll</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Videos</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="mt-3 line"></div>

        <p class="mt-4 ml-5">Streaming</p>
        <v-list-item class="mt-2" v-for="item in streamingLinks" :key="item.to" :to="item.to">
          <v-list-item-action>
            <v-icon>{{item.icon}}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{item.title}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="mt-3 line"></div>

        <p class="mt-4 ml-5">Team Management</p>
        <v-list-item class="mt-2" to="/Members">
          <v-list-item-action>
            <v-icon>mdi-account-multiple-outline</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Members</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="mt-3 line"></div>
        
        <p class="mt-4 ml-5">Analytics</p>
        <v-list-item class="mt-2" to="/Analytics">
          <v-list-item-action>
            <v-icon>mdi-poll</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Streaming Analytics</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="mt-3 line"></div>

        <p class="mt-4 ml-5">Upgrades</p>
        <v-list-item class="mt-2" to="/Upgrade">
          <v-list-item-action>
            <v-icon>mdi-star</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Upgrade Plan</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="mt-3 line"></div>

        <p class="mt-4 ml-5">Refferal / Affiliate</p>
        <v-list-item class="mt-2" to="/Affiliate">
          <v-list-item-action>
            <v-icon>mdi-currency-usd</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Affiliate Program</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="mt-3 line"></div>

        <p class="mt-4 ml-5">Help</p>
        <v-list-item class="mt-2" to="/Faq">
          <v-list-item-action>
            <v-icon>mdi-frequently-asked-questions</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>FAQ’s</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item class="mt-2" to="/Contact">
          <v-list-item-action>
            <v-icon>mdi-phone-outline</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Contact Us</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
       
      </v-list>
      
    </v-navigation-drawer>
    <v-main light>
        <Nuxt />
    </v-main>
    <!-- <v-footer fixed="false" class="align-self-center" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer> -->
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      drawer: true,
      streamingLinks: [
        {
          icon: 'mdi-microphone-outline',
          title: 'Pre-recorded Stream',
          to: '/Streaming'
        },
        {
          icon: 'mdi-movie-open-cog-outline',
          title: 'Real-Time Stream',
          to: '/RealTime'
        },
        {
          icon: 'mdi-calendar-month-outline',
          title: 'Schedules',
          to: '/Schedules'
        },
        {
          icon: 'mdi-history',
          title: 'Streaming History',
          to: '/History'
        },
      ],
    }
  }
}
</script>

<style>
.line {
  height: 1px;
  margin-top: 10px;
  background: #464757;
}
</style>