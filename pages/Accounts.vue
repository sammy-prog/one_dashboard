<template>
  <div class="mt-8 mx-8">
    <p class="header__titles mt-5">Connected Accounts</p>
    <p class="sub__title">Add streaming accounts to OneStream</p>
    <v-row class="connected__section pa-6 mt-4">
      <div
        v-for="accounts in connectedAccounts"
        :key="accounts.name"
        class="d-flex connected__accounts px-3 pt-3 mt-2 ml-2"
      >
        <img class="pa-1" :style="{ 'background-color': accounts.color, 'border-radius': '5px' }" :src="accounts.image" alt="img" height="30px" width="30px" />
        <p class="ml-2 mt-1" :style="{ color: accounts.color }">
          {{ accounts.name }}
        </p>
      </div>
    </v-row>
    <Footer />
  </div>
</template>

<script>
import Footer from '../components/Footer.vue'
export default {
  name: "Accounts",
  components: {
    Footer
  },
  data() {
    return {
      connectedAccounts: [
          {
          image: "/connected/image 22.png",
          color: "#2AB577",
          name: "trovo",
        },
        {
          image: "/connected/image 19.png",
          color: "#444951",
          name: "Custom RTMP",
        },
        {
          image: "/connected/image 20.png",
          color: "#2065FB",
          name: "hopin",
        },
        {
          image: "/connected/image 27.png",
          color: "#F9922B",
          name: "Socio",
        },
        {
          image: "/connected/image 28.png",
          color: "#E47F82",
          name: "Bumbaser",
        },
        {
          image: "/connected/image 29.png",
          color: "#1CB0CF",
          name: "Phone Live",
        },
        {
          image: "/connected/image 30.png",
          color: "#FED230",
          name: "dlive",
        },
        {
          image: "/connected/image 31.png",
          color: "#FC3744",
          name: "View Stub",
        },
        {
          image: "/connected/image 32.png",
          color: "#444951",
          name: "dacast",
        },
        {
          image: "/connected/image 33.png",
          color: "#FD8424",
          name: "WOWZA",
        },
        {
          image: "/connected/image 34.png",
          color: "#1B4EEC",
          name: "Stage Ten",
        },
        {
          image: "/connected/image 35.png",
          color: "#F9E937",
          name: "Mobcrush",
        },
        {
          image: "/connected/image 36.png",
          color: "#444951",
          name: "Afreeca Tv",
        },
        {
          image: "/connected/image 37.png",
          color: "#1DACFC",
          name: "dailymotion",
        },
        {
          image: "/connected/image 39.png",
          color: "#27A359",
          name: "Picarto",
        },
        {
          image: "/connected/image 46.png",
          color: "#25B7F1",
          name: "Muvi",
        },
        {
          image: "/connected/image 47.png",
          color: "#0C677F",
          name: "Flow Player",
        },
        {
          image: "/connected/image 48.png",
          color: "#000000",
          name: "Loots",
        },
        {
          image: "/connected/image 49.png",
          color: "#F8DF32",
          name: "Kakao Tv",
        },
        {
          image: "/connected/image 50.png",
          color: "#FD9626",
          name: "Huya.com",
        },
        {
          image: "/connected/image 51.png",
          color: "#2FAFE3",
          name: "Bilibili",
        },
        {
          image: "/connected/image 51.png",
          color: "#C74E43",
          name: "Bear Tv",
        },
        {
          image: "/connected/image 53.png",
          color: "#222D63",
          name: "Douyu.com",
        },
        {
          image: "/connected/image 54.png",
          color: "#5F1BC9",
          name: "Nimo Tv",
        },
        {
          image: "/connected/image 55.png",
          color: "#23DC7E",
          name: "Naver Tv",
        },
        {
          image: "/connected/image 56.png",
          color: "#5EF7FE",
          name: "VLive",
        },
        {
          image: "/connected/image 57.png",
          color: "#4F24FB",
          name: "M-Xcloud",
        },
        {
          image: "/connected/image 70.png",
          color: "#C74E43",
          name: "nanolive",
        },
        {
          image: "/connected/image 71.png",
          color: "#279ADE",
          name: "Only Fans",
        },
        {
          image: "/connected/image 72.png",
          color: "#DD3037",
          name: "Fc2 Live",
        },
        {
          image: "/connected/image 73.png",
          color: "#253155",
          name: "G G!!",
        },
        {
          image: "/connected/image 74.png",
          color: "#1A1A1A",
          name: "MLG",
        },
        {
          image: "/connected/image 75.png",
          color: "#2673C0",
          name: "IBM",
        },
        {
          image: "/connected/image 76.png",
          color: "#222D63",
          name: "OK.Ru",
        },
        {
          image: "/connected/image 77.png",
          color: "#FD5B1F",
          name: "Chew Tv",
        },
        {
          image: "/connected/image 78.png",
          color: "#2D2D2D",
          name: "Vapers Tv",
        },
        {
          image: "/connected/image 79.png",
          color: "#2A2A2A",
          name: "Breakers Tv",
        },
        {
          image: "/connected/image 80.png",
          color: "#132F4C",
          name: "Vaughn Live",
        },
      ],
    };
  },
  head() {
    return {
      title: "Accounts",
      meta: [
        {
          hid: "Accounts",
          name: "Accounts",
          content: "Accounts connected for OneStream",
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
.sub__title{
  font-size: 16.5px;
  color: #444951;
}
.connected__accounts {
  border: 1px solid #E8E7E7;
  border-radius: 5px;
  width: 200px;
  max-height: 50px;
  cursor: pointer;
}
.connected__section {
  background-color: white !important;
  border-radius: 10px;
}
</style>