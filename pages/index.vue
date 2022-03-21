<template>
  <div class="mt-8">
    <div class="d-flex">
      <v-row class="justify-space-between mx-8">
        <v-col cols="12" md="3">
          <HeaderCard color="#EA7BF4" primaryIcon="mdi-play-circle-outline" mainTitle="ONGOING LIVE STREAMS" SecondaryIcon="mdi-plus-circle" subTitle="New Stream"/>
        </v-col>
        <v-col cols="12" md="3">
          <HeaderCard color="#FCB263" primaryIcon="mdi-calendar-month-outline" mainTitle="SCHEDULED STREAMS" SecondaryIcon="mdi-view-list" subTitle="List Schdules"/>
        </v-col>
        <v-col cols="12" md="3">
          <HeaderCard color="#56B4FC" primaryIcon="mdi-apps" mainTitle="CONNECTED ACCOUNTS" SecondaryIcon="mdi-plus-circle" subTitle="Add Account"/>
        </v-col>
        <v-col cols="12" md="3">
          <HeaderCard color="#59606C" primaryIcon="mdi-puzzle" mainTitle="FREE PLAN" SecondaryIcon="mdi-star" subTitle="My Subscription" description="1 Parallel Stream" description1="5 Mins each stream"/>
        </v-col>
      </v-row>
    </div>
  </div>
</template>

<script>
import HeaderCard from '../components/cards/HeaderCard.vue'
export default {
  name: 'IndexPage',
  components: {
    HeaderCard
  },
  head() {
    return {
        title: 'Dashboard',
        meta: [
            {
                hid: "Dashboard",
                name: "Dashboard",
                content: "Dashboard for OneStream"
            }
        ]
    }
  }
}
</script>

<style>

</style>