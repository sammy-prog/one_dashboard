<template>
  <div class="mt-8 mx-8">
    <p class="header__titles mt-5">Team Members</p>
    <p class="sub__title">
      Manage your team members
    </p>
    <v-row class="mt-6 pa-8 align-center" style="background-color: white!important;border-radius: 10px; min-height: 60vh">
        <v-col cols="12" md="6" class="list__paragraphs">
            <ul>
                <li><p>Team management is a powerful feature that allows you to add multiple team members to work & collaborate seamlessly.</p></li>
                <li><p>Team members (based on their roles) can schedule and manage live streams for your connected social accounts.</p></li>
            </ul>
            <div class="ml-3">
                <h3 style="color:#444951; font-size:18px" class="mt-8">Standard or Professional subscription required to use team management. <br> Team Managemet FAQs</h3>
                <v-btn dark color="#4854EE" class="text-none mt-5">Upgrade to Activate</v-btn>
            </div>
        </v-col>
        <v-col cols="12" md="6" class="">
            <img  width="100%" src="/5235.jpg" alt="group">
        </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
    name: 'Members',
    head() {
    return {
      title: "Members",
      meta: [
        {
          hid: "Members",
          name: "Members",
          content: "Members for OneStream",
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
</style>