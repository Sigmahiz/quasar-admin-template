<template>
  <q-layout>
    <q-page-container>
      <q-page class="flex bg-image flex-center">
        <q-card v-bind:style="$q.screen.lt.sm?{'width': '80%'}:{'width':'30%'}">
          <q-card-section style="display:flex;justify-content:center;align-items:center;min-height:100px">
            <q-img src="http://150.136.117.63:8080/sigmahisDemo/css/bootstrap/img/_big_color.png" style="width:200px;height:auto"/>
          </q-card-section>
          <q-card-section>
            <q-form
              class="q-gutter-md"
            >
              <q-input
                filled
                v-model="username"
                label="Username"
                lazy-rules
                id="username"
              />

              <q-input
                type="password"
                filled
                v-model="password"
                label="Password"
                lazy-rules
                id="password"
              />

              <div>
                <q-btn label="Login" to="/" type="button" color="primary"/>
              </div>
            </q-form>
          </q-card-section>
        </q-card>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script setup>

import {ref,onMounted} from 'vue'
import { driver } from "driver.js";

const username= ref('Pratik')
const password= ref('12345')

onMounted(()=>{
  const driverObj = driver({
  showProgress: true,
  steps: [
    { element: '#username', popover: { title: 'Animated Tour Example', description: 'Here is the code example showing animated tour. Let\'s walk you through it.', side: "left", align: 'start' }},
    { element: 'code .line:nth-child(1)', popover: { title: 'Import the Library', description: 'It works the same in vanilla JavaScript as well as frameworks.', side: "bottom", align: 'start' }},
    { element: 'code .line:nth-child(2)', popover: { title: 'Importing CSS', description: 'Import the CSS which gives you the default styling for popover and overlay.', side: "bottom", align: 'start' }},
    { element: 'code .line:nth-child(4) span:nth-child(7)', popover: { title: 'Create Driver', description: 'Simply call the driver function to create a driver.js instance', side: "left", align: 'start' }},
    { element: 'code .line:nth-child(18)', popover: { title: 'Start Tour', description: 'Call the drive method to start the tour and your tour will be started.', side: "top", align: 'start' }},
    { element: 'a[href="/docs/configuration"]', popover: { title: 'More Configuration', description: 'Look at this page for all the configuration options you can pass.', side: "right", align: 'start' }},
    { popover: { title: 'Happy Coding', description: 'And that is all, go ahead and start adding tours to your applications.' } }
  ]
});

driverObj.drive();
})
</script>

<style>

.bg-image {
  background: #fff url(http://150.136.117.63:8080/sigmahisDemo/css/bootstrap/img/bg2.jpg) no-repeat fixed top;
  background-size: cover;
}
</style>
