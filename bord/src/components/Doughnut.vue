<template >
  <div class=" grid-col-1 p-4 dark:bg-white/5 rounded shadow-2xl">
<h1 class=" text-2xl pl-2"> Revenue Socurces</h1>
  <div class=" max-h-[400px] w-full">
  <Doughnut :data="lineDAta" :options="animationOPtion" :key="key"></Doughnut>
  </div>
    
  </div>
</template>
<script setup>
import { ref,onMounted } from 'vue'; 
import {Doughnut} from 'vue-chartjs';  
import {
  Chart as ChartJS, Title, Tooltip, Legend,LineElement,CategoryScale,LinearScale,PointElement,ArcElement,
  plugins,} from "chart.js";
ChartJS.register(Title,Tooltip,Legend,LineElement, CategoryScale, LinearScale,PointElement,ArcElement);

const lineDAta=ref({
labels:["june","july","august","september"],
datasets:[{
 // label:"Salse",
  data:[1000,2000,4000,5000],
  backgroundColor:["red","sky","yellow","green"],
  tension:0.1,  
}]
})

const animationOPtion=ref({
  responsive:true,
  maintainAspectRatio:false,
  cutout:80,
  animation:{
    duration:1000,
    easing:"easeInOutQuad",
  
    
     loop:false,
    

  },
  plugins:{
    legend:{
      display:true,
      position:"right",
      labels:{
        boxwidth:3,
        padding:15,
        color:"blue",
        font:{
          size:14,
          weight:"bold",
        }
      }
    },
    tooltip:{
        callback:{
          labels:function(data){data.row}
        }
      }

  },  

})
const key=ref(0);
onMounted(  ()=>{
key.value++

})
</script>
<script>
export default {
  name:"ChartJs",
}
</script>
 