<template>
  <div class="mt-8 mx-8">
    <p class="header__titles mt-5">Real-time Multicasting</p>
    <p class="sub__title">
      Send stream to OneStream using any third party tool like OBS, Zoom, XSplit
      etc. and multicast seamlessly to connected social accounts.
    </p>
    <v-row class="mt-6 pa-8" style="background-color: white!important;border-radius: 10px; min-height: 60vh">
        <v-col cols="12" md="6" class="list__paragraphs">
            <ul>
                <li><p>Using Real-time streaming feature, you can send stream to OneStream from any third party tool.</p></li>
                <li><p>Just use your OneStream's Server URL & Key and send the stream.</p></li>
                <li><p>Once the video signal is received, multicast or restream to multiple social accounts simultaneously.</p></li>
            </ul>
            <div class="ml-3">
                <h3 style="color:#444951; font-size:18px" class="mt-8">Standard or Professional subscription is required to use real-time streaming feature. FAQs</h3>
                <v-btn dark color="#4854EE" class="text-none mt-5">Activate Real-time Streaming</v-btn>
            </div>
        </v-col>
        <v-col cols="12" md="6" class="">
            <img width="100%" height="280px" src="/Group.png" alt="group">
        </v-col>
    </v-row>
    <Footer />
  </div>
</template>

<script>
import Footer from "../components/Footer.vue";
export default {
  name: "RealTime",
  components: {
    Footer,
  },
  head() {
    return {
      title: "RealTime",
      meta: [
        {
          hid: "RealTime",
          name: "RealTime",
          content: "RealTime streaming for OneStream",
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
.list__paragraphs ul{
    list-style: none;
}
.list__paragraphs li::before {
    content: "\2022";
    color: #FDA74B;
    display: inline-block;
    width: 1em;
    margin-left: -1em;
}
.list__paragraphs p{
    margin-top: -23px;
}
</style>