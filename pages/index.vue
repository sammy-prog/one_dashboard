<template>
  <div class="mt-8 mx-8">
    <div class="d-flex">
      <v-row class="justify-space-between">
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
    <div class="mt-8 streaming__section">
      <p class="header__titles">Streaming Overview</p>
      <div class="stream__section mt-5 px-5 py-8">
        <v-row>
          <v-col cols="12" md="6">
            <div class="d-md-flex d-xs-block">
              <SmallStreamCards icon="mdi-gamepad-circle-outline" title="Streams Counts"/>
              <SmallStreamCards icon="mdi-history" title="Overview"/>
            </div>
            <div class="d-md-flex d-xs-block mt-2">
              <SmallStreamCards icon="mdi-timer-sand-empty" title="Available Duration"/>
              <SmallStreamCards icon="mdi-account-group" title="Team Members"/>
            </div>
          </v-col>
          <v-col cols="12" md="6">
            <div class="d-flex justify-space-between bordered">
              <div>
                <p>ADD-ONS applied to subscription</p>
                <v-btn dark color="#4854EE" class="text-none mt-2">More about ADD-ONS</v-btn>
              </div>
              <div>
                <p style="font-size: 30px; font-weight: 700">(0)</p>
              </div>
            </div>
            <div style="border: 1px solid #E8E7E7;padding: 5px;border-radius: 10px;" class="mt-8">
              <p style="font-size: 16px;" class="mt-2 ml-3">Number of streams by platforms (Last Week)</p>
            </div>
          </v-col>
        </v-row>
      </div>
    </div>
    <v-row class="mt-5">
      <v-col cols="12" md="6">
        <p class="header__titles">Ongoing Live Streams</p>
        <div class="live__stream__section py-3 px-7 mt-5">
          <div class="d-flex justify-space-between align-center">
            <div class="d-flex live__card align-center">
              <v-icon size="35" dark>mdi-play-circle-outline</v-icon>
              <div class="ml-4 mt-4">
                  <p style="font-size:25px;font-weight:700">04</p>
                  <p style="margin-top:-15px;">Events  3h : 00m</p>
              </div>     
            </div>
            <v-btn class="text-none px-8" color="#FEA74C">Today</v-btn>
          </div>
          <div v-for="i in 3" :key="i" class=" mt-6">
            <div class="d-flex justify-space-between align-end">
              <div class="mb-2">
                <p>Live Event on social gathering</p>
                <v-btn outlined color="#91969D" class="text-none">3 Account <v-icon color="#91969D">mdi-chevron-down</v-icon></v-btn>
              </div>
              <p style="color: #6D737C">Date Sheet 12:00</p>
            </div>
            <hr class="mt-2" color="#F0F0F0">
          </div>
          <div class="mt-16"></div>
        </div>
      </v-col>

      <v-col cols="12" md="6">
        <p class="header__titles">Schedules Streams</p>
        <div class="live__stream__section py-3 px-7 mt-5">
          <div class="d-flex justify-space-between align-center">
            <div class="d-flex live__card align-center">
              <v-icon size="35" dark>mdi-calendar-month-outline</v-icon>
              <div class="ml-4 mt-4">
                  <p style="font-size:25px;font-weight:700">05</p>
                  <p style="margin-top:-15px;">Events Today</p>
              </div>     
            </div>
            <v-btn class="text-none px-8" color="#FEA74C">This Week</v-btn>
          </div>
          <div v-for="i in 3" :key="i" class=" mt-2">
            <div class="d-flex justify-space-between align-end">
              <div class="mb-2">
                <p>Live Event on social gathering</p>
                <p style="color: #4854EE;margin-top:-15px">Live Stream</p>
                <v-btn style="margin-top:-10px" outlined color="#91969D" class="text-none">3 Account <v-icon color="#91969D">mdi-chevron-down</v-icon></v-btn>
              </div>
              <p style="color: #6D737C">Date Sheet 12:00</p>
            </div>
            <hr class="mt-2" color="#F0F0F0">
          </div>
        </div>
      </v-col>
    </v-row>
    <p class="header__titles mt-5">Connected Accounts</p>
    <v-row class="connected__section py-5 align-center">
        <v-col cols="12" md="3">
          <div class="py-3 px-3">
            <div class="d-flex justify-space-between align-center">
              <div class="d-flex live__card align-center mt-2">
                <v-icon size="35" dark>mdi-lan-connect</v-icon>
                <div class="ml-4 mt-4">
                    <p style="font-size:25px;font-weight:700">08</p>
                    <p style="margin-top:-15px;">Accounts Connected</p>
                </div>     
              </div>
            </div>
          </div>
        </v-col>
        <v-col cols="12" md="7" class="d-flex">
          <v-row>
            <div v-for="accounts in connectedAccounts" :key="accounts.name" class="d-flex connected__accounts px-3 pt-3 mt-2 ml-2">
            <img :src="accounts.image" alt="img" height="30px" width="30px" />
            <p class="ml-2 mt-1" :style="{ 'color': accounts.color }">{{accounts.name}}</p>
          </div>
          </v-row>
        </v-col>
        <v-col cols="12" md="2">
          <div class="d-flex">
            <v-icon color="#FDA74B">mdi-format-list-bulleted</v-icon>
            <p class="mt-2 ml-2" style="color: #FDA74B;text-decoration: underline;text-underline-offset:2px">View List</p>
          </div>
          <div>
            <v-btn dark color="#4854EE" class="no-uppercase"><v-icon class="mr-2">mdi-plus-circle</v-icon>Add More</v-btn>
          </div>
        </v-col>
    </v-row>
    <v-row>
      
      <v-col cols="12" md="6">
        <p class="header__titles mt-5">Number of Streams by Platform</p>
        <div class="chart px-2 py-10">
          <BarChart :data="barChartData" :options="barChartOptions" :height="280" />
        </div>
      </v-col>
      <v-col cols="12" md="6">
        <p class="header__titles mt-5">Number of Streams by Platform</p>
        <div class="chart px-2 py-10">
          <LineChart :data="barChartData" :options="barChartOptions" :height="280" />
        </div>
      </v-col>
    </v-row>
    <Footer />
  </div>
</template>

<script>
import HeaderCard from '../components/cards/HeaderCard.vue'
import SmallStreamCards from '../components/cards/SmallStreamCard.vue'
import BarChart from "../components/charts/BarChart.vue";
import LineChart from '../components/charts/LineChart.vue'
import Footer from '../components/Footer.vue'
export default {
  name: 'IndexPage',
  components: {
    HeaderCard,
    SmallStreamCards,
    BarChart,
    LineChart,
    Footer
  },
  data() {
    return {
      connectedAccounts: [
        {
          image: '/connected/facebook (6) 1.png',
          color: '#4267B2',
          name: 'Page'
        },
        {
          image: '/connected/facebook (6) 1.png',
          color: '#4267B2',
          name: 'Group'
        },
        {
          image: '/connected/facebook (6) 1.png',
          color: '#4267B2',
          name: 'Profile'
        },
        {
          image: '/connected/youtube (4) 1.png',
          color: '#F61C0D',
          name: 'Youtube'
        },
        {
          image: '/connected/instagram (5) 1.png',
          color: '#FF9899',
          name: 'Instagram'
        },
        {
          image: '/connected/twitch 1.png',
          color: '#C36EFF',
          name: 'Twitch'
        },
        {
          image: '/connected/steam-logo (1) 1.png',
          color: '#0D2242',
          name: 'Steam'
        },
        {
          image: '/connected/vimeo 1.png',
          color: '#2AB8E8',
          name: 'Vimeo'
        },
      ],
      barChartData: {
        labels: [
          "Jan",
          "Feb",
          "Mar",
          "Apr",
          "May",
          "Jun",
          "Jul",
          "Aug",
          "Sep",
          "Oct",
          "Nov",
          "Dec",
        ],
        datasets: [
          {
            label: "Monthly viewers (k)",
            data: [2.1, 1.3, 3.4, 2.5, 2.8, 1.5, 0.8, 2.2, 3.01, 2, 1.5, 2.6],
            backgroundColor: "#7F87F3",
            barThickness: 16,
            maxBarThickness: 16,
            fill: false,
            borderColor: '#7F87F3',
            lineTension: 0.4
          },
        ],
      },
      barChartOptions: {
        responsive: true,
        legend: {
          display: false,
        },
        tooltips: {
          backgroundColor: "#7F87F3",
        },
        scales: {
          xAxes: [
            {
              gridLines: {
                display: false,
              },
            },
          ],
          yAxes: [
            {
              ticks: {
                beginAtZero: false,
                min: 0,
                max: 4,
                stepSize: 1,
                callback: function(label, index, labels) {
                switch (label) {
                    case 0:
                        return '0';
                    case 1:
                        return '1k';
                    case 2:
                        return '2k';
                    case 3:
                        return '3k';
                    case 4:
                        return '4k';
                    case 5:
                        return '5k';
                }
            }
              },
              gridLines: {
                display: true,
                drawBorder: false,
                borderDash: [8, 4],
              },
            },
          ],
        },
      },
    }
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
.stream__section {
  background-color: white !important;
  border-radius: 10px;
}
.bordered {
  border: 1px solid #E8E7E7;
  padding: 15px;
  border-radius: 10px;
}

.live__card i{
  background-color: #BDC2FF;
  padding-left: 14px;
  padding-right: 14px;
  border-radius: 10px;
  height: 60px;
}
.live__stream__section {
  background-color: white !important;
  border-radius: 10px;
  height: 540px;
}
.header__titles {
  font-size: 26px;
  font-weight: 600;
  color: #444951;
}
.connected__section {
  background-color: white !important;
  border-radius: 10px;
  min-height: 190px;
  
}
.connected__accounts {
  border: 1px solid #E8E7E7;
  border-radius: 5px;
  width: 200px;
  max-height: 50px;
  cursor: pointer;
}
.chart {
  background-color: white !important;
  border-radius: 10px;
}
</style>