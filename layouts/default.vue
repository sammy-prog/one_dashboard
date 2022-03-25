<template>
  <v-app>
    <v-app-bar
      color="white"
      dense
      app
      height="70"
      elevation="0"
      style="border-bottom: 1px solid #D3D0D3 !important;"
    >
    <v-row class="align-center justify-space-between px-8">
      <div>
        <v-btn dark color="#4854EE" class="no-uppercase"><v-icon class="mr-2">mdi-plus-circle</v-icon>New Stream</v-btn>
      </div>
      <div class="d-none d-md-block">
        <div class="d-flex" style="margin-top:20px">
          <nuxt-link style="text-decoration: none !important" to="/Schedules"><v-icon class="mx-4">mdi-calendar-month-outline</v-icon></nuxt-link> 
          <nuxt-link style="text-decoration: none !important" to="/Videos"><v-icon class="mx-4">mdi-play-circle-outline</v-icon></nuxt-link>
          <v-menu transition="scale-transition" bottom max-width="280px">
            <template v-slot:activator="{ on }">
              <v-flex icon v-on="on">
                <v-avatar style="cursor:pointer" class="transparent avatar__custom" size="45">
                  <v-badge
                    :content="notifications.length"
                    :value="notifications.length"
                    offset-x="12"
                    offset-y="22"
                  >
                    <v-icon style="margin-top:-20px"> mdi-bell-outline </v-icon>
                  </v-badge>
                </v-avatar>
              </v-flex>
            </template>
            <v-card style="margin-top:48px" elevation="16">
              <v-list-item-content class="list__notif">
                <li v-for="notify in notifications" :key="notify">
                  <p class="ml-5 mt-1 pa-1 mr-5">{{ notify }}</p>
                  <hr class="horizontal__line"/>
                </li>
              </v-list-item-content>
              <p v-if="!notifications.length" class="ml-4 mt-3 pa-1 mr-2">No new notifications!</p>
              <v-btn v-if="notifications.length" @click="clearNotifications" style="font-size:12px" class="text-none mb-4 ml-4">Clear All</v-btn>
            </v-card>
          </v-menu>
          
        </div>  
      </div>
      <div class="d-none d-md-flex ">
        <v-menu transition="scale-transition" bottom min-width="220px">
          <template v-slot:activator="{ on }">
            <v-flex icon v-on="on">
              <div style="cursor: pointer" class="d-flex">
                <v-avatar size="48px">
                  <img
                    alt="Avatar"
                    src="/Behance-Profile-pic 1.png">
                  </v-avatar>
                <p class="mt-4 ml-2">Samuel LB</p>
                <v-icon>mdi-chevron-down</v-icon>
              </div>
            </v-flex>
          </template>
          <v-card style="margin-top:60px" elevation="16">
            <v-list-item-content>
              <div class="dropdown__menu mt-2">
                <p class="ml-4" style="cursor:pointer">Profile</p>
                <hr class="horizontal__line"/>
                <p class="ml-4 mt-3 py-1" style="cursor:pointer">Approvals</p>
                <hr class="horizontal__line"/>
                <p class="ml-4 mt-3 py-1" style="cursor:pointer">Streams</p>
                <hr class="horizontal__line"/>
                <v-btn style="font-size:14px" class="text-none my-3 ml-4"> Log Out </v-btn>
              </div>
            </v-list-item-content>
          </v-card>
        </v-menu>

      </div>
      
      <v-spacer class="sm6 d-sm-none" ></v-spacer>
      <v-app-bar-nav-icon class="sm6 d-sm-none" @click="drawer = true"></v-app-bar-nav-icon>
    </v-row>
    </v-app-bar>

    <v-navigation-drawer
      v-model="drawer"
      app
      dark
      :permanent="!$vuetify.breakpoint.xsOnly"
      color="#222433"
    >
      <img class="mt-4 ml-5" style="cursor:pointer" height="37" width="144" src="/onestreamlogo.png" alt="onestream_logo" />
      <div class="line"></div>
      <v-list class="mb-16">
        <v-list-item active-class="sidenav__link" class="mt-2" to="/">
          <v-list-item-action>
            <v-icon>mdi-apps</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Dashboard</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item active-class="sidenav__link" class="mt-2" to="/Accounts">
          <v-list-item-action>
            <v-icon>mdi-account-outline</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Accounts</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="mt-3 line"></div>

        <p class="mt-4 ml-5">OneStream Storage</p>
        <v-list-item active-class="sidenav__link" class="mt-2" to="/Videos">
          <v-list-item-action>
            <v-icon>mdi-play-circle-outline</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Videos</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="mt-3 line"></div>

        <p class="mt-4 ml-5">Streaming</p>
        <v-list-item active-class="sidenav__link" class="mt-2" v-for="item in streamingLinks" :key="item.to" :to="item.to">
          <v-list-item-action>
            <v-icon>{{item.icon}}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{item.title}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="mt-3 line"></div>

        <p class="mt-4 ml-5">Team Management</p>
        <v-list-item active-class="sidenav__link" class="mt-2" to="/Members">
          <v-list-item-action>
            <v-icon>mdi-account-multiple-outline</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Members</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="mt-3 line"></div>
        
        <p class="mt-4 ml-5">Analytics</p>
        <v-list-item active-class="sidenav__link" class="mt-2" to="/Analytics">
          <v-list-item-action>
            <v-icon>mdi-poll</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Streaming Analytics</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="mt-3 line"></div>

        <p class="mt-4 ml-5">Upgrades</p>
        <v-list-item active-class="sidenav__link" class="mt-2" to="/Upgrade">
          <v-list-item-action>
            <v-icon>mdi-star</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Upgrade Plan</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="mt-3 line"></div>

        <!-- <p class="mt-4 ml-5">Refferal / Affiliate</p>
        <v-list-item active-class="sidenav__link" class="mt-2" to="/Affiliate">
          <v-list-item-action>
            <v-icon>mdi-currency-usd</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Affiliate Program</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <div class="mt-3 line"></div> -->

        <!-- <p class="mt-4 ml-5">Help</p>
        <v-list-item active-class="sidenav__link" class="mt-2" to="/Faq">
          <v-list-item-action>
            <v-icon>mdi-frequently-asked-questions</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>FAQ’s</v-list-item-title>
          </v-list-item-content>
        </v-list-item> -->
      </v-list>
      
    </v-navigation-drawer>
    <v-main light>
        <Nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      drawer: true,
      notifications: [
        'You recieved invitation for a stream!',
        'Please confirm your account settings.',
        'You have 50 new viewers!'
      ],
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
  },
  methods: {
    clearNotifications(){
      this.notifications = []
    },
  }
}
</script>

<style>
* {
  font-family: 'Quicksand', sans-serif;
}
body{
  overflow: hidden;
}
.v-application {
  background-color: #F4F5F8 !important;
}
.line {
  height: 1px;
  margin-top: 10px;
  background: #464757;
}
.v-navigation-drawer__content{
  overflow-y: hidden !important;
}
.v-navigation-drawer__content:hover{
  overflow-y: auto !important;
}
.v-navigation-drawer__content::-webkit-scrollbar {
  width: 5px !important;    
}                                 
.v-navigation-drawer__content::-webkit-scrollbar-thumb {
  background: rgb(255, 255, 255, 0.4) !important;                                
  border-radius: 20px !important;
}
.sidenav__link {
  border-left: 5px solid #FEA74C !important;
  border-radius: 5px 0px 0px 5px !important;
  color: #FEA74C !important;
}

.v-list-item--link:before{
  background-color: #3B3D51 !important;
  left: 10px !important;
  border-top-left-radius: 5px !important;
  border-bottom-left-radius: 5px !important;
}
.no-uppercase {
  text-transform: unset !important;
}
.list__notif li{
  list-style: none !important;
}

.dropdown__menu p{
  color: black;
  font-size: 16px;
  font-weight: 350;
}
.dropdown__menu p:hover{
  cursor: pointer;
  color: #7a99be;
}
hr.horizontal__line {
    border: 0;
    height: 1px;
}

hr.horizontal__line, hr.horizontal__line:before {
    background: radial-gradient(ellipse at center, rgba(72, 84, 238, 0.4) 0%,rgb(255, 255, 255) 75%);
}
</style>