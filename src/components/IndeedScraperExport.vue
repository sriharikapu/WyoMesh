<template>
  <form>
    <md-card class="md-layout-item md-size-90">
      <md-card-header>
        <div class="md-title">Results</div>
        <md-table>
          <md-table-head>Device ID</md-table-head>
          <md-table-head>Site Name</md-table-head>
          <md-table-head>Date</md-table-head>
          <md-table-head>Type</md-table-head>
          <md-table-head>Priority</md-table-head>
          <md-table-head>Latitude</md-table-head>
          <md-table-head>Longitude</md-table-head>
          <md-table-head>Picture</md-table-head>
          <md-table-head>Sign Off</md-table-head>
          <md-table-row v-for="(incident, index) in this.incidents" :key="index">
            <md-table-cell> {{ incident.deviceId }} </md-table-cell>
            <md-table-cell> {{ incident.siteName }} </md-table-cell>
            <md-table-cell> {{ incident.incidentDateTime }} </md-table-cell>
            <md-table-cell> {{ incident.incidentType }} </md-table-cell>
            <md-table-cell> {{ incident.incidentPriority }} </md-table-cell>
            <md-table-cell> {{ incident.latitude }} </md-table-cell>
            <md-table-cell> {{ incident.longitude }} </md-table-cell>
            <md-table-cell> <a :href=incident.picture>{{ incident.picture }}</a> </md-table-cell>
            <md-table-cell> <a v-on:click="signOff(index)">{{ incident.isSignedOff }}</a> </md-table-cell>
          </md-table-row>
        </md-table>
      </md-card-header>
    </md-card>
    
    <!-- <md-snackbar :md-duration="4000" :md-active.sync="showSnackbar" md-persistent>
      <span v-if="resultsScraped">Results Scraped!</span>
      <span v-else>An error occurred. Please make sure you entered a search term.</span>
    </md-snackbar> -->
  </form>
</template>

<script>

export default {
  name: 'IndeedScraperExport',
  data() {
    return ({
      incidents: [
        {
          "deviceId": "5b94f16b1f0cbcc17ff21081",
          "index": 0,
          "isActive": true,
          "siteName": "Antelope Coal Mine",
          "incidentDateTime": "Tuesday, April 1, 2014 7:58 AM",
          "incidentType": "Fire Origin Detected",
          "incidentPriority": "Low",
          "latitude": "43.7017699",
          "longitude": "-105.6854778",
          "picture": "https://ipfs.io/ipfs/QmZUC47Rj5bLkFUcKbWfkn6HevGXtj2G8fNE4dMs1tZFyS",
          "isSignedOff": "Pending"
        },
        {
          "deviceId": "5b94f16b58297f324382ea3c",
          "index": 1,
          "isActive": true,
          "siteName": "Antelope Coal Mine",
          "incidentDateTime": "Friday, February 21, 2014 9:14 PM",
          "incidentType": "Wildlife Detected",
          "incidentPriority": "Medium",
          "latitude": "43.5838514",
          "longitude": "-105.8036484",
          "picture": "https://ipfs.io/ipfs/QmewEGjChxaVA2hCXnLYULFqySHkyQpb9MTAhyfozdu5mB",
          "isSignedOff": "Pending"
        },
        {
          "deviceId": "5b94f16b43b5d594acafc67d",
          "index": 2,
          "isActive": true,
          "siteName": "Antelope Coal Mine",
          "incidentDateTime": "Monday, August 10, 2015 4:06 AM",
          "incidentType": "Fault in Structure Detected",
          "incidentPriority": "Low",
          "latitude": "43.6590526",
          "longitude": "-105.9867821",
          "picture": "https://ipfs.io/ipfs/Qmesad8ckm8msmv41XAYi6xRoE3zsNT92b2wTVdftHv246",
          "isSignedOff": "Pending"
        },
        {
          "deviceId": "5b94f16b7729f6eb5fe872ca",
          "index": 4,
          "isActive": true,
          "siteName": "Antelope Coal Mine",
          "incidentDateTime": "Sunday, January 8, 2017 4:05 AM",
          "incidentType": "Fire/Smoke Detected",
          "incidentPriority": "Low",
          "latitude": "43.7049433",
          "longitude": "-105.4340305",
          "picture": "https://ipfs.io/ipfs/QmQdP45ZUVW6m3kqGh32x3d39WFBDT1vqKgpQASHBKsfQR",
          "isSignedOff": "Pending"
        },
        {
          "deviceId": "5b94f16ba492568a8459c665",
          "index": 5,
          "isActive": true,
          "siteName": "Antelope Coal Mine",
          "incidentDateTime": "Saturday, December 13, 2014 8:09 PM",
          "incidentType": "Critical Thermal Detected",
          "incidentPriority": "Critical",
          "latitude": "43.7004714",
          "longitude": "-105.922604",
          "picture": "https://ipfs.io/ipfs/QmSQu8LpYMfJsoENv8kasoBLgRQVFNT5q1545h1KaGkS6j",
          "isSignedOff": "Pending"
        },
        {
          "deviceId": "5b94f16b8895fd9072866e98",
          "index": 6,
          "isActive": true,
          "siteName": "Antelope Coal Mine",
          "incidentDateTime": "Thursday, June 5, 2014 1:41 PM",
          "incidentType": "Intruder Detected",
          "incidentPriority": "Low",
          "latitude": "43.8052023",
          "longitude": "-105.3626719",
          "picture": "https://ipfs.io/ipfs/QmSQu8LpYMfJsoENv8kasoBLgRQVFNT5q1545h1KaGkS6j",
          "isSignedOff": "Pending"
        },
        {
          "deviceId": "5b94f16bc8a06b25f9ab029d",
          "index": 7,
          "isActive": true,
          "siteName": "Antelope Coal Mine",
          "incidentDateTime": "Thursday, August 24, 2017 11:00 AM",
          "incidentType": "Intruder Detected",
          "incidentPriority": "High",
          "latitude": "43.5858583",
          "longitude": "-105.6205794",
          "picture": "https://ipfs.io/ipfs/QmewEGjChxaVA2hCXnLYULFqySHkyQpb9MTAhyfozdu5mB",
          "isSignedOff": "Pending"
        },
        {
          "deviceId": "5b94f16b20dd0e39295916f3",
          "index": 11,
          "isActive": true,
          "siteName": "Antelope Coal Mine",
          "incidentDateTime": "Friday, November 28, 2014 5:00 PM",
          "incidentType": "Landslide Risk Detected",
          "incidentPriority": "High",
          "latitude": "43.5178567",
          "longitude": "-105.5532832",
          "picture": "https://ipfs.io/ipfs/QmZUC47Rj5bLkFUcKbWfkn6HevGXtj2G8fNE4dMs1tZFyS",
          "isSignedOff": "Pending"
        },
        {
          "deviceId": "5b94f16bee96edd5b2230d26",
          "index": 12,
          "isActive": true,
          "siteName": "Antelope Coal Mine",
          "incidentDateTime": "Sunday, May 14, 2017 11:26 PM",
          "incidentType": "Landslide Risk Detected",
          "incidentPriority": "Low",
          "latitude": "43.7149289",
          "longitude": "-105.4933068",
          "picture": "https://ipfs.io/ipfs/QmewEGjChxaVA2hCXnLYULFqySHkyQpb9MTAhyfozdu5mB",
          "isSignedOff": "Pending"
        },
        {
          "deviceId": "5b94f16bfb52a5602febd6fb",
          "index": 13,
          "isActive": true,
          "siteName": "Antelope Coal Mine",
          "incidentDateTime": "Monday, May 28, 2018 12:20 PM",
          "incidentType": "Wildlife Detected",
          "incidentPriority": "High",
          "latitude": "43.8459526",
          "longitude": "-105.4324474",
          "picture": "https://ipfs.io/ipfs/QmSQu8LpYMfJsoENv8kasoBLgRQVFNT5q1545h1KaGkS6j",
          "isSignedOff": "Pending"
        }
      ]
    })
  },
  computed: {
    
  },
  methods: {
    signOff: function (index) {
      this.incidents[index].isSignedOff = "Signed";
    }
  },
}
</script>

<style scoped>
.md-card {
  margin: auto;
  padding-bottom: 20px;
  margin: 20px auto;
}

.md-card-actions {
  display: inline;
}

.md-table-cell {
  text-align: left;
}
</style>
