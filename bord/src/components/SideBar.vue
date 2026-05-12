<template >
  <aside class=" block  w-72 min-h-screen bg-base-100 py-6 backdrop-blur-md 
   backdrop:[--webkit-backdrop-filter:blur(20px)]
     dark:bg-white/15  border-r border-gray-200 dark:border-gray-700">
    <h1 class="text-2xl text-center pb-6 pt-2"> AdminPanel</h1>

    <nav class=" w-[80%]   mx-auto   flex flex-col gap-4 justify-center"> 
    <ul class=" flex flex-col gap-6">
      <li  v-for="item in items" :key="item.id">

<button @click="toggleItem(item)" 
relo="menuitem"
:aria-expanded=" !!item.subItem && item.open"
:aria-haspopup="!!item.subItem"
 class=" flex w-full hover:bg-black/10 dark:hover:bg-white/20  px-2 py-1 rounded-sm">
<div class=" flex items-center gap-4 ">
   <Icon :icon="item.icon"></Icon>
<div>{{ item.name }}</div>
</div>
<span v-if="item.subItem " class=" ml-auto " >
 <Icon :icon="item.open ? 'line-md:chevron-down':'line-md:chevron-right'"  ></Icon>
 </span>
</button>
      

<ul v-if="item.activ && item.subItem" class=" flex flex-col gap-2 ml-2 mt-2   border-l border-gray-200 dark:border-gray-700    ">  
<li v-for="(itemt, index) in item.subItem" :key="index" class="hover:bg-black/10 dark:hover:bg-white/10 rounded-sm px-2 py-1 ml-3" >{{ itemt.name }}</li>
</ul>
      </li>
    </ul>
    </nav>
  </aside>
</template> 
<script setup>
//import { Activity } from 'react';
//import { openBlock } from 'vue';
import {ref} from 'vue';

const items = ref([
  { id: 1, name: 'Dashboard', icon: 'line-md:home', subItem: null, activ: false , open: false},
  { id: 2, name: 'Analytics', icon: 'icon-park-outline:chart-line', subItem: null, activ: false , open: false  },
  { id: 3, name: 'Reports', icon: 'line-md:document-list', subItem: [{ name: 'User All'},{name: 'Add now' },{name:"Recens & Pormmition"}], activ: false, open: false},
    { id: 4, name: 'Users', icon: 'line-md:account', subItem:[{ name: 'User All'},{name: 'Add now' },{name:"Recens & Pormmition"}], activ: true , open: true},
     { id: 5, name: 'Products', icon: 'mdi:shopping-outline', subItem:[{ name: 'User All'},{name: 'Add now' },{name:"Recens & Pormmition"}], activ: false , open: false},
  { id: 6, name: 'Messages', icon: 'line-md:email', subItem: null, activ: false, open: false},
  { id: 7, name: 'Settings', icon: 'line-md:cog-filled', subItem: null, activ: false, open:false},

]);

const toggleItem = (item) => {
  if (item.subItem) {
    item.open = !item.open;
    item.activ = !item.activ;
  }
};  


</script>
<script>
export default {
  name:"SideBar",
}
</script> 
 