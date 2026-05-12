<template >
    <div class=" drawer drawer-start lg:drawer-open  w-full">
    <input type="checkbox" name="my-drawer" id="my-drawer" class=" drawer-toggle">
    <h1>chek</h1>
<div class=" drawer-side"> dfffds
     <label for="my-drawer" class=" drawer-overlay"></label>
      <SideBar></SideBar>
      </div>
       <div  class=" drawer-content flex flex-col gap-5  p-4">
     <NavBer @toggle-drawer="toggleDrawer"  @toggle-theme="toggleTheme" :isdrakMode="isDarkMode"></NavBer>
         <Data ></Data >
     
     <div class=" grid grid-cols-1 lg:grid-cols-2 gap-5">
         <ChartJs></ChartJs>
         <Doughnut></Doughnut>
         </div>
         <RecentData></RecentData>
         <BarChart></BarChart>

         
         </div>
    </div>
</template>
<script setup>
import { ref,watch,onMounted } from 'vue';
import SideBar from './components/SideBar.vue'; 
import NavBer from './components/NavBer.vue';
import Data from './components/Data.vue';
import ChartJs from './components/ChartJs.vue';
import Doughnut from './components/Doughnut.vue';
import RecentData from './components/RecentData.vue'; 
import BarChart from './components/BarChart.vue'; 





const toggleDrawer =()=>{
   const chked=document.getElementById('my-drawer');   
     chked.checked=!chked.checked;
  //document.getElementById('my-drawer').checked=chked;
}
const isDarkMode = ref(false);

const toggleTheme = () => {
  isDarkMode.value = !isDarkMode.value;

}; 

// this is for when the page is loaded the theme is set according to the local storage or the system preference
onMounted(()=>{
  // this is for when the page is loaded the theme is get from the local storage or the system preference
const lcal=localStorage.getItem('data')
const windowDarkMode=window.matchMedia('(prefers-color-scheme: dark)').matches

  if(lcal=='dark' || (!lcal && windowDarkMode) ){
  isDarkMode.value=true

}
else {
  isDarkMode.value=false
}

// this is for when the page is loaded the theme is set according to the system preference

const theme=document.getElementsByTagName('html')[0]
  if(isDarkMode.value){
  theme.setAttribute('data-theme','dark')

}
else {
  theme.setAttribute('data-theme','light')

}


})
 // this is for when the theme is changed the theme is set according to the system preference
watch(isDarkMode,()=>{
  const theme=document.getElementsByTagName('html')[0]

   if(isDarkMode.value){
   theme.setAttribute('data-theme','dark')
   localStorage.setItem('data','dark')

  }
  else{
    theme.setAttribute('data-theme','light')
   localStorage.setItem('data','light')

  }
})






</script>
<script>
export default {
    name:"RecentData",

}
</script>