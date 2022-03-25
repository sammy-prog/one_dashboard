<template>
  <div class="mt-8 mx-8">
    <p class="header__titles mt-5">History</p>
    <p class="sub__title">No history for this account.</p>
    <v-row class="pa-4 mt-6" style="background-color:white !important;border-radius: 10px">
        <v-col style="color:#444951" cols="12" md="8">
            <h3>No Pre-Reorded Streaming History</h3>
            <p class="mt-2">You haven't streamed any video yet on this account, hence no stream history is available.</p>
            <p>Remember, there is no limit on streams per month. Every subscription plan has different number of slots available at any given time.</p>
            <v-btn dark color="#4854EE" class="text-none mt-5">Schedule Recorded Stream</v-btn>
        </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
    name: 'History',
    head() {
    return {
      title: "History",
      meta: [
        {
          hid: "History",
          name: "History",
          content: "History for OneStream",
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