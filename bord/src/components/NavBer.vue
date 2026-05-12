<template >
   <header class=" navber  shadow-xl sticky top-0 z-50ar backdrop-blur-md 
   backdrop:[--webkit-backdrop-filter:blur(20px)]  bg-base-100  dark:bg-white/20  flex items-center justify-between px-4 py-2">
   
   <nav class=" lg:hidden flex items-center">

   <button @click="$emit('toggle-drawer')" class="btn btn-square mx-1 btn-ghost backdrop-blur-md backdrop:[--webkit-backdrop-filter:blur(20px)]">
   <Icon icon="line-md:close-to-menu-alt-transition" class=" w-5 h-5"></Icon>
   </button>

   </nav>

   <section class=" flex-1"> 
   <div class=" form-control">
   <input type="search" class=" input w-48" placeholder="Search">
   </div>
   </section>


<section> 
        <button class="btn btn-circle   btn-ghost  dark:bg-white/20   
        b  backdrop-blur-md backdrop:[--webkit-backdrop-filter:blur(20px)]"
  @click="$emit('toggle-theme')" > 
 <Icon v-if="isdrakMode" icon="line-md:sunny-outline-to-moon-alt-loop-transition"   class="
   w-8 h-8  "></Icon>
   <Icon v-else icon="line-md:moon-alt-to-sunny-outline-loop-transition" class="   w-8 h-8  "></Icon>

</button>

<div class=" dropdown  dropdown-button dropdown-end">

<button class=" btn btn-circle ml-4  avatar btn-ghost border    dark:bg-white/20 
        bg-base-100  backdrop-blur-md backdrop:[--webkit-backdrop-filter:blur(20px)]">
 
 <figure class="  w-8 h-8 rounded-full overflow-hidden   bg-gray-200  dark:bg-gray-600">
    
 <img src=" " alt="User Image" class=" w-full h-full">
 </figure>



  
</button>

 <ul tabindex="0" class=" menu menu-compact dropdown-content mt-2 p-2 shadow-lg 
bg-base-100 rounded-box dark:bg-white/15  w-56">

<li><a href="#">Home</a></li>
<li><a href="#">About</a></li>
<li><a href="#">Contact</a></li>

</ul>
 </div>

 
</section>

   </header>
</template>
<script setup>
import { Icon } from '@iconify/vue';
import { ref } from 'vue';
defineProps({
   isdrakMode:{
type:Boolean,

   required:true,

   },
});
defineEmits(['toggle-drawer','toggle-theme'])
</script>
<script>
export default {
    name:"NavBer"
}
</script>