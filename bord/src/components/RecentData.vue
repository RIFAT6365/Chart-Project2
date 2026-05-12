<template>
  <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
    <div class="col-span-1 lg:col-span-2 bg-base-100 px-4 pr-8 py-3 shadow-2xl rounded-md">
      <h1 class="text-2xl ml-3">Recent Order</h1>
      <div class="w-full ml-3">
        <table class="table ">
          <thead>
            <tr>
              <th>Order ID</th>
              <th>Customer</th>
              <th>Date</th>
              <th>Amount</th>
              <th>State</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(data, index) in items" :key="index">
              <td>{{ data.order }}</td>
              <td>{{ data.customer }}</td>
              <td>{{ data.data }}</td>
              <td>{{ data.ammount }}</td>
              <td>{{ data.states }}</td>
            </tr>
          </tbody>
        </table>
        <button class="py-2 px-4 bg-indigo-600 ml-auto rounded-sm block mt-2">View All</button>
      </div>
    </div>

    <!-- Recent Activity -->
    <div class="col-span-1 bg-base-100 px-4 py-3 shadow-xl rounded-md">
      <h1 class="card card-title text-left py-4">Recent Activity</h1>

      <ul class="timeline timeline-vertical w-full">
        <li v-for="(itemt, index) in itemstt" :key="index">
          
          <!-- Even index: বাম দিকে -->
          <template v-if="index % 2 === 0">
            <div class="timeline-start timeline-box">{{ itemt.name }}</div>
            <div class="timeline-middle">
              <div class="w-3 h-3 rounded-full bg-purple-700"></div>
            </div>
            <hr />
          </template>

          <!-- Odd index: ডান দিকে -->
          <template v-else>
            <hr />
            <div class="timeline-middle">
              <div class="w-3 h-3 rounded-full bg-purple-700"></div>
            </div>
            <div class="timeline-end timeline-box">{{ itemt.name }}</div>
            <hr />
          </template>

        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import {ref} from 'vue'
const items=ref([
{order:'#001',customer:'Jhon dos', data:'2005-05-16', ammount:'$125.00',states:'Complate'},
{order:'#002',customer:'jane shan', data:'2005-05-18', ammount:'$89.00',states:'Pandding'},
{order:'#003',customer:'Refen Jshone', data:'2005-05-30', ammount:'$234.00',states:'Canceled'},

])



const itemstt=ref([
  {name:'Limit Use',left:true},
  {name:'New order',right:true},
  {name:'System Update',left:true},
  {name:'Unic page',right:true},
  {name:'New order',left:true},

])
</script>
<script>
export default {
  name:'RecentData'
}
</script>
