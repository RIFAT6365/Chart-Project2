<template >
  <div class=" grid-col-1 p-4 dark:bg-white/5 rounded shadow-2xl">
<h1 class=" text-2xl pl-2"> Monthly Revuenuw</h1>
  <div class=" h-[400px] ">
  <Line :data="lineDAta" :options="animationOPtion" :key="key"></Line>
  </div>
    
  </div>
</template>
<script setup>
import { ref,onMounted } from 'vue'; 
import {Line} from 'vue-chartjs';  
import {
  Chart as ChartJS, Title, Tooltip, Legend,LineElement,CategoryScale,LinearScale,PointElement,
  plugins,} from "chart.js";
ChartJS.register(Title,Tooltip,Legend,LineElement, CategoryScale, LinearScale,PointElement);

const lineDAta=ref({
labels:["june","july","august","september","october","november"],
datasets:[{
  label:"Salse",
  data:[10,30,30,80,50,60],
  backgroundColor:"red",
  borderwidth:20,
  borderColor:"red",
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
        borderwidth:8,
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
      grid:{
        color:"rgba(255,99,132,0.2)",
      },
      ticks:{
        beginAtZero:true,
        color:"green",
      }
    },
     x:{
      grid:{
        color:"rgba(255,99,132,0.2)",
      },
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
  name:"ChartJs",
}
</script>
 