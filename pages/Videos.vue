<template>
  <div class="mt-8 mx-8">
    <p class="header__titles mt-5">My stored videos</p>
    <p class="sub__title">Personal video storage</p>
    <v-row>
      <div class="d-flex mt-4">
        <div class="ml-6" v-for="storage in storages" :key="storage.name">
          <img
            :style="{
              'background-color': storage.color,
              'border-radius': '50%',
              'padding': '5px',
              'cursor':'pointer'
            }"
            :src="storage.image"
            alt="img"
            height="35px"
            width="35px"
          />
          <p class="mt-1" :style="{ color: storage.color }">
            {{ storage.name }}
          </p>
        </div>
      </div>
    </v-row>
    <v-row class="mt-6 justify-space-between">
        <v-col cols="12" md="6">
            <p class="sub__title">Video storage capacity depends on the subscription plan. Videos that are not used for 60 days will be deleted automatically</p>
        </v-col>
        <v-col cols="12" md="6" class="align-self-end">
            <v-text-field prepend-inner-icon="mdi-magnify" style="width:50%;margin-left: 50%" solo placeholder="Search"></v-text-field>
        </v-col>
    </v-row>
    <v-row class="pa-4" style="background-color:white !important;border-radius: 10px">
        <v-col style="color:#444951" cols="12" md="8">
            <h3>Video Storage</h3>
            <p class="mt-2">Video storage is available for paid users.</p>
            <p>With video storage, when you upload a video to stream live, it is automatically saved for later use, so you do not have to upload it again. You can simply reuse the stored videos to schedule a new live.</p>
            <p>Videos that are not reused for more than 60 days will be removed automatically.</p>
            <v-btn dark color="#4854EE" class="text-none mt-5">Upgrade to Activate</v-btn>
        </v-col>
        <v-col style="color:#444951" cols="12" md="4">
            <div class="d-flex mt-10">
                <v-progress-circular :size="120" :width="15" :value="73" color="#FEA74C">73%</v-progress-circular>
                <div class="ml-4 mt-7">
                    <p>Personal storage</p>
                    <p>730 MB of 1 GB used</p>
                </div>
            </div>
        </v-col>
    </v-row>
    <Footer />
  </div>
</template>

<script>
import Footer from '../components/Footer.vue'
export default {
  name: "Videos",
  components: {
    Footer
  },
  data() {
    return {
      storages: [
        {
          image: "/storage/image 81.png",
          color: "#1273DD",
          name: "Drop Box",
        },
        {
          image: "/storage/image 89.png",
          color: "#4F9E62",
          name: "Google Drive",
        },
        {
          image: "/storage/image 90.png",
          color: "#2B7BD2",
          name: "One Drive",
        },
        
        {
          image: "/storage/image 91.png",
          color: "#008DFF",
          name: "Zoom Cloud",
        },
        {
          image: "/storage/image 92.png",
          color: "#1375F3",
          name: "Box Storage",
        },
        {
          image: "/storage/image 94.png",
          color: "#5B59FB",
          name: "Frame.io",
        },
      ],
    };
  },
  head() {
    return {
      title: "Videos",
      meta: [
        {
          hid: "Videos",
          name: "Videos",
          content: "Videos storage options for OneStream",
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
</style>