<template >
  <div class=" grid-col-1 p-4 dark:bg-white/5 rounded shadow-2xl">
<h1 class=" text-2xl pl-2"> Monthly Revuenuw</h1>
  <div class=" h-[400px] ">
  <Bar :data="lineDAta" :options="animationOPtion" :key="key"></Bar>
  </div>
    
  </div>
</template>
<script setup>
import { ref,onMounted } from 'vue'; 
import {Bar} from 'vue-chartjs';  
import {
  Chart as ChartJS, Title, Tooltip, Legend,LineElement,CategoryScale,LinearScale,PointElement,BarElement,
  plugins,} from "chart.js";
ChartJS.register(Title,Tooltip,Legend,LineElement, CategoryScale, LinearScale,PointElement,BarElement);

const lineDAta=ref({
labels:["june","july","august","september","october","november"],
datasets:[{
  label:"Salse",
  data:[10,30,30,80,50,60],
  backgroundColor:["red","sky","yellow","green"],
  tension:0.1,  
}]
})

const animationOPtion=ref({
  responsive:true,
  maintainAspectRatio:false,
  animation:{
    duration:1000,
    easing:"easeInOutQuad",
  
    
     loop:false,
    

  },
  plugins:{
    legend:{
      display:true,
      position:"top",
      labels:{
        borderWidth:8,
        color:"blue",
        font:{
          size:14,
          weight:"bold",
        }
      }
    },
 
     
  },  
  scales:{
    y:{
      
      ticks:{
        beginAtZero:true,
        color:"green",
      }
    },
     x:{
    
      ticks:{
        beginAtZero:true,
        color:"green",
      }
    }
  }
})
const key=ref(0);
onMounted(  ()=>{
key.value++

})
</script>
<script>
export default {
  name:"BarChart",
}
</script>
 