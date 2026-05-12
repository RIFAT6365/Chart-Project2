<template >
    <div class="w-full bg-base-100 backdrop-blur-md backdrop:[--webkit-backdrop-filter:blur(20px)]">
        <ul class=" grid grid-cols-2 lg:grid-cols-4 gap-6">
        <li v-for="(item, index) in items" :key="index" class=" card card-body bg-base-100 shadow-2xl rounded-lg hover:bg-black/5 dark:hover:bg-white/5">
        <h1 class=" card-title text-sm text-gray-400 dark:text-gray-200">{{ item.title }}</h1>
        <div class=" font-bold text-4xl">{{ item.money }}</div>
        <div class=" flex items-center gap-2">
        <span :class="item.symbole=='+' ? 'text-green-500': 'text-red-500'" >{{ item.symbole }}</span>
        <div :class="item.symbole=='+' ? 'text-green-500': 'text-red-500'">{{ item.data }}</div>
        </div>
        </li>
        </ul>
    </div>
</template>

<script setup>
import {ref} from 'vue'
const items=ref([
{title: 'Total User', money:'12,345',data:'34% total grow user', symbole:'+'},
{title: 'Total Earnig', money:'$43,556',data:' 23 growng eran', symbole:'+'},

{title: 'New User', money:'56',data:'total monthly user', symbole:'-'},
{title: 'Avarge user', money:'56',data:'total monthly data', symbole:'+'},


])
</script>
<script>
export default {
    
}
</script>
