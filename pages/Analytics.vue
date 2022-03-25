<template>
  <div class="mt-8 mx-8">
    <p class="header__titles mt-5">Team Members</p>
    <p class="sub__title">Manage your team members</p>
    <v-row
      class="mt-6 pa-8 align-center"
      style="background-color: white !important; border-radius: 10px"
    >
      <v-col cols="12" md="12" style="color: #6d737c">
        <h3 style="color: #444951">Analytics</h3>
        <p class="mt-2">
          Detailed live analytics are available from Standard Plan onwards. You
          can still access basic analytics available on Dashboard.
        </p>
        <img
          class="profile__pic mr-6"
          src="/Behance-Profile-pic 2.png"
          alt="profile"
        />
        <div>
          <h3 style="color: #444951">John Doe</h3>
          <p class="mt-2">
            Lorem Ipsum is simply dummy text of the printing and typesetting
            industry. Lorem Ipsum has been the industry's standard dummy text
            ever since the 1500s
          </p>
          <p class="mt-7">
            when an unknown printer took a galley of type and scrambled it to
            make a type specimen book. It has survived not only five centuries.
          </p>
        </div>
      </v-col>
    </v-row>
    <v-row class="mt-10">
      <v-col cols="12" md="6">
        <div class="chart px-2 py-10">
          <BarChart
            :data="barChartData"
            :options="barChartOptions"
            :height="280"
          />
        </div>
      </v-col>
      <v-col cols="12" md="6">
        <div class="chart px-2 py-10">
          <LineChart
            :data="barChartData"
            :options="barChartOptions"
            :height="280"
          />
        </div>
      </v-col>
    </v-row>
    <v-row class="px-7 py-2 mt-5 justify-space-between" style="background-color: white !important; border-radius: 10px; min-height:30vh">
        <div v-for="progress in progressBars" :key="progress.value" class="mt-10">
            <v-progress-circular :size="120" :width="15" :value="progress.value" :color="progress.color">{{progress.value}}%</v-progress-circular>
        </div>
    </v-row>
    <v-row class="justify-end">
        <v-btn dark color="#4854EE" class="text-none mt-10 text-right">Upgrade Plan</v-btn>
    </v-row>
    <Footer />
  </div>
</template>

<script>
import BarChart from "../components/charts/BarChart.vue";
import LineChart from "../components/charts/LineChart.vue";
import Footer from "../components/Footer.vue";
export default {
  name: "Analytics",
  components: {
    BarChart,
    LineChart,
    Footer,
  },
  data() {
    return {
      progressBars: [
          {
              value: 20,
              color: '#FEA74C'
          },
          {
              value: 40,
              color: '#7F88F4'
          },
          {
              value: 60,
              color: '#FEA74C'
          },
          {
              value: 80,
              color: '#7F88F4'
          },
          {
              value: 100,
              color: '#FEA74C'
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
            borderColor: "#7F87F3",
            lineTension: 0.4,
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
                callback: function (label, index, labels) {
                  switch (label) {
                    case 0:
                      return "0";
                    case 1:
                      return "1k";
                    case 2:
                      return "2k";
                    case 3:
                      return "3k";
                    case 4:
                      return "4k";
                    case 5:
                      return "5k";
                  }
                },
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
    };
  },
  head() {
    return {
      title: "Analytics",
      meta: [
        {
          hid: "Analytics",
          name: "Analytics",
          content: "Analytics for OneStream",
        },
      ],
    };
  },
};
</script>

<style>
.header__titles {
  font-size: 26px;
  font-weight: 600;
  color: #444951;
}
.sub__title {
  font-size: 16.5px;
  color: #444951;
}
.profile__pic {
  height: 160px;
  width: 160px;
  box-shadow: 0px 0px 7px 2px #a1a1a1;
  border-radius: 7px;
  float: left;
}
</style>