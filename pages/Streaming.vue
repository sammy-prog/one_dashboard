<template>
  <div class="mt-8 mx-8">
    <p class="header__titles mt-5">New Stream</p>
    <p class="sub__title">Upload Video to Stream</p>
    <div class="mt-6 pa-8" style="background-color: white!important;border-radius: 10px; min-height: 90vh">
        <p class="sub__title">Recommended Video Settings</p>
        <p>Allowed: <span style="color:#5F69F0"> mov, mp4, mkv, webm, m4v</span></p>
        <div style="border: 1px solid #E8E7E7; height: 300px;border-radius: 10px 10px 0px 0px;">
            <v-row class="justify-center" style="background-color: #3A3D50; width:100%; margin:auto; border-radius: 10px 10px 0px 0px;">
                <p class="mt-2" style="color:white">Upload Video File</p>
            </v-row>
            <v-row>
                <v-col class="justify-center" style="border-right: 1px solid #E8E7E7" cols="12" md="6">
                    <div style="border: 1px dashed #E8E7E7;height: 200px" class="streamContainer pa-10">
                        <div class="d-flex mt-2">
                            <input type="file" name="fileUpload" id="fileUpload" style="display: none">
                            <label class="ml-6 mt-2" for="fileUpload">
                                <img src="/storage/cloud-computing (3) 1.png" alt="cloud">
                            </label>
                            <img src="/storage/stream 2.png" alt="stream">
                        </div>
                        <p style="color:#6D737C;text-align:center" class="mt-4">Upload or Record</p>
                    </div>
                </v-col>
                <v-col cols="12" md="6">
                    <div style="border: 1px dashed #E8E7E7;height: 200px" class="streamContainer pa-10">
                        <div class="d-flex mt-2">
                            <img src="/storage/cloud-computing (3) 1.png" alt="cloud">
                        </div>
                        <p style="color:#6D737C;text-align:center" class="mt-4">Previous Uploads</p>
                    </div>
                </v-col>
                <p class="mt-5 mx-auto">Upload max 5 GB directly from your device or Record using camera feature.</p>
            </v-row>
        </div>
        <div class="mt-14" style="border: 1px solid #E8E7E7; height: 200px;border-radius: 10px 10px 0px 0px;">
            <v-row class="justify-center" style="background-color: #3A3D50; width:100%; margin:auto; border-radius: 10px 10px 0px 0px;">
                <p class="mt-2" style="color:white">Import VIA Cloud Storage</p>
            </v-row>
            <v-row class="justify-center mt-10">
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
                <p class="mt-4 mx-auto">There is no file size limit when importing video directly from your cloud storage.</p>
            </v-row>
        </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Footer from '../components/Footer.vue'
export default {
    name: 'Streaming',
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
      title: "Streaming",
      meta: [
        {
          hid: "Streaming",
          name: "Streaming",
          content: "Streaming options",
        },
      ],
    };
  },
}
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
.streamContainer {
    width: 50%;
    margin: auto;
}
.streamContainer img {
    background-color: #FEA74C;
    height: 50px;
    width: 50px;
    padding: 10px;
    border-radius: 50%;
    margin: auto;
    cursor: pointer;
}
</style>