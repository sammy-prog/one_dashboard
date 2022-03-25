<template>
  <div class="mt-8 mx-8">
    <p class="header__titles mt-5">Scheduled Streams</p>
    <p class="sub__title">Scheduled streams management.</p>
    <v-row class="d-flex align-end justify-space-between mt-10">
        <div>
            <p class="sub__title ml-2">Once the scheduled video is live streamed, the slot is again available. Enjoy unlimited streaming.</p>
        </div>
        <div class="d-flex mr-2">
            <div style="cursor:pointer" class="d-flex align-start">
                <v-icon color="#FDA74B">mdi-format-list-bulleted</v-icon>
                <p style="color: #FDA74B" class="ml-2">List</p>
            </div>
            <div style="cursor:pointer" class="d-flex ml-5 align-start">
                <v-icon color="#6872F0">mdi-calendar-month-outline</v-icon>
                <p style="color: #6872F0" class="ml-2">Calender</p>
            </div>
        </div>
    </v-row>
    <v-row class="pa-6 mt-6" style="background-color:white !important;border-radius: 10px">
        <v-col style="color:#444951" cols="12" md="8">
            <h3>Recommended Video Settings</h3>
            <p class="mt-3">Keep filling up your scheduling slots with new streams..</p>
            <p>Remember, there is no limit on streams per month. Every subscription plan has different number of slots available at any given time.</p>
            <v-btn dark color="#4854EE" class="text-none mt-7">Schedule New Stream</v-btn>
        </v-col>
        <v-col style="color:#444951" cols="12" md="4">
            <div style="margin" class="d-flex mt-10">
                <v-progress-circular :size="120" :width="15" :value="8" color="#FEA74C">8%</v-progress-circular>
                <div class="ml-4 mt-7">
                    <p>Scheduling Queue Slots </p>
                    <p>0 of 1 used</p>
                </div>
            </div>
        </v-col>
    </v-row>
    <v-row class="pa-6 mt-10" style="background-color:white !important;border-radius: 10px">
        <v-col cols="12" md="3">
            <img width="100%" src="/thumb_436939__9kcvu0brj_hllsxcuvs 1.png" alt="thumb">
        </v-col>
        <v-col cols="12" md="3">
            <div class="d-flex">
                <v-icon style="margin-top:-40px" color="#4854EE">mdi-history</v-icon>
                <div>
                    <table class="table__schedule ml-2">
                        <tr>
                            <td>1</td>
                            <td>19</td>
                            <td>43</td>
                            <td>45</td>
                        </tr>
                        <tr>
                            <td>Day</td>
                            <td>Hour</td>
                            <td>Min</td>
                            <td>Sec</td>
                        </tr>
                    </table>
                </div>
            </div>
            <p class="mt-1" style="font-size: 18px;color: #444951">Top 10 Budgerigar -Daniel</p>
            <v-btn dark color="#FEA74C" class="text-none">Queued</v-btn>
        </v-col>
        <v-col cols="12" md="3">
            <p>Scheduled</p>
            <div class="d-flex align-start">
                <v-icon color="#FDA74B">mdi-calendar-month-outline</v-icon>
                <p class="ml-2">31 Jul, Sat, 16:03 (Karachi)</p>
            </div>
            <p class="mt-3">Scheduled By</p>
            <div class="d-flex align-start">
                <v-icon color="#FDA74B">mdi-account</v-icon>
                <p class="ml-2">Jack</p>
            </div>
        </v-col>
        <v-col cols="12" md="3">
            <p>Channel</p>
            <div class="d-flex align-start">
                <v-icon color="#FDA74B">mdi-youtube</v-icon>
                <p class="ml-2">Rai Slah(YouTube Event))</p>
            </div>
            <p class="mt-3">Type</p>
            <div class="d-flex align-start">
                <v-icon color="#FDA74B">mdi-flash</v-icon>
                <p class="ml-2">Pre-recorded Stream</p>
            </div>
        </v-col>
        <div class="d-flex ml-2 schedule__icons">
            <v-icon color="#858796">mdi-information-variant</v-icon>
            <v-icon color="#858796">mdi-pencil-outline</v-icon>
            <v-icon color="#858796">mdi-trash-can-outline</v-icon>
            <v-icon color="#858796">mdi-autorenew</v-icon>
        </div>  
    </v-row>
    <Footer />
  </div>
</template>

<script>
import Footer from "../components/Footer.vue";
export default {
  name: "Schedules",
  components: {
    Footer,
  },
  head() {
    return {
      title: "Schedules",
      meta: [
        {
          hid: "Schedules",
          name: "Schedules",
          content: "Schedules for OneStream",
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
table{
    border-collapse: collapse;
    border-style: hidden;
    background-color: #B6BBF8;
    border-radius: 7px;
    color: white;
}
.table__schedule td, table th{
    padding: 5px;
    border: 1px solid #DADDFB;
}
.schedule__icons i{
    border: 1px solid #E3E1E1;
    padding: 4px;
    border-radius: 7px;
    margin-left: 7px;
    cursor: pointer;
}
</style>