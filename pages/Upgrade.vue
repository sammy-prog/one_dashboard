<template>
  <div class="mt-8 mx-8">
    <p class="header__titles mt-5">You are currently using Free Plan</p>
    <p class="sub__title">Manage your upgrade plan</p>
    <v-row
      class="mt-14 mb-8"
      style="background-color: white !important; border-radius: 10px"
    >
      <v-col class="pricing__col" cols="3">
        <h3>FREE</h3>
        <p class="mt-4">No credit card required!</p>
        <div class="pricing mt-4">
          <p v-for="plan in freePlan" :key="plan">
            <span><v-icon>mdi-check-circle-outline</v-icon></span
            >{{ plan }}
          </p>
        </div>
        <h3 class="mt-7">$ 0 / month</h3>
        <v-btn class="no-uppercase mt-4" dark color="#4854EE"
          >Try For Free</v-btn
        >
      </v-col>
      <v-col class="pricing__col" cols="3">
        <h3>BASIC</h3>
        <p class="mt-4">Billed annually</p>
        <div class="pricing mt-4">
          <p v-for="plan in freePlan" :key="plan">
            <span><v-icon>mdi-check-circle-outline</v-icon></span
            >{{ plan }}
          </p>
        </div>
        <h3 class="mt-7">$ 8 / month</h3>
        <v-btn class="no-uppercase mt-4" dark color="#4854EE"
          >Get Started</v-btn
        >
      </v-col>
      <v-col class="pricing__col" cols="3">
        <h3>STANDARD</h3>
        <p class="mt-4">Billed annually</p>
        <div class="pricing mt-4">
          <p v-for="plan in freePlan" :key="plan">
            <span><v-icon>mdi-check-circle-outline</v-icon></span
            >{{ plan }}
          </p>
        </div>
        <h3 class="mt-7">$ 32 / month</h3>
        <v-btn class="no-uppercase mt-4" dark color="#4854EE"
          >Get Started</v-btn
        >
      </v-col>
      <v-col class="pricing__col" cols="3">
        <h3>PROFESSIONAL</h3>
        <p class="mt-4">PROFESSIONAL</p>
        <div class="pricing mt-4">
          <p v-for="plan in freePlan" :key="plan">
            <span><v-icon>mdi-check-circle-outline</v-icon></span
            >{{ plan }}
          </p>
        </div>
        <h3 class="mt-7">$ 74 / month</h3>
        <v-btn class="no-uppercase mt-4" dark color="#4854EE"
          >Get Started</v-btn
        >
      </v-col>
    </v-row>
    <Footer />
  </div>
</template>

<script>
import Footer from "../components/Footer.vue";
export default {
  name: "Upgrade",
  components: {
    Footer,
  },
  data() {
    return {
      freePlan: [
        "Unlimited Live Streaming",
        "Pre-recorded Streaming",
        " No Real-time Streaming",
        "No Multicasting",
        "1 Queued stream at a time",
        "No Playlist Streaming",
        "5 min max / recorded stream",
        "1 Social account",
        "5 GB max video file size",
        "5 min Camera recording",
        "5 min Screen capturing",
      ],
    };
  },
  head() {
    return {
      title: "Upgrade",
      meta: [
        {
          hid: "Upgrade",
          name: "Upgrade",
          content: "Upgrade for OneStream",
        },
      ],
    };
  },
};
</script>

<style>
.pricing span {
  margin-right: 10px;
}
.pricing i {
  color: #fda74b !important;
}
.pricing p {
  font-size: 14px;
}
.pricing__col:not(:first-of-type) {
  border-left: 1px solid #eeeeee;
}
</style>