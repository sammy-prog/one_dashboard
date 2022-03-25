<template>
    <div  class="pa-3">
        <hr class="mt-10" style="color: #3A3C4F;opacity:20%">
        <v-row class="justify-space-between align-center">
            <p style="color:#A8A9B1" class="mt-5">&copy; {{ new Date().getFullYear() }} Developed by Samuel L. Bekele</p>
            <div class="d-flex socials mt-2"> 
            <img style="width: 21px; height: 20px;" src="/social/facebook 1.png" alt="fb">
            <img style="width: 24px; height: 24px;" src="/social/twitter 1.png" alt="twitter">
            <img style="width: 20px; height: 20px;" src="/social/linkedin 1.png" alt="linkedin">
            <img style="width: 26px; height: 26px;" src="/social/youtube 4.png" alt="utube">
            </div>
        </v-row>
    </div>
</template>

<script>
export default {
    name: 'Footer'
}
</script>

<style>
.socials img{
    margin-right: 30px !important;
    cursor: pointer;
}
</style>