<template>


  <Sidebar v-model="visible">
    <h2>Test</h2>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
  </Sidebar>



<Menubar :model="items">
    <template #start>
    
    <div class="flex items-center content-center gap-4">
          <Button outlined severity="secondary" icon="pi pi-bars" @click="visible = true"/>

        <a class="flex items-center self-center" href="">
        <svg  width="82" height="16" viewBox="0 0 82 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd" clip-rule="evenodd" d="M16.6613 0L0.447256 13.6503L0 16H2.33599L14.8958 5.43151L12.8713 16H15.9351L19 0H16.6613Z" fill="#F3652B"/>
              <path fill-rule="evenodd" clip-rule="evenodd" d="M22.0645 0L21.4854 3.02307H32.0678L19.4534 13.6444L19 16H34.9355L35.5146 12.9769H24.9323L37.5495 2.3533L38 0H22.0645Z" fill="#F3652B"/>
              <path fill-rule="evenodd" clip-rule="evenodd" d="M41.0003 0L38 16H40.9997L44 0H41.0003Z" fill="#F3652B"/>
              <path fill-rule="evenodd" clip-rule="evenodd" d="M47.0644 0L44 16H59.9356L63 0H47.0644ZM49.5536 3.02291H59.3487L57.4422 12.9769H47.6472L49.5536 3.02291Z" fill="#F3652B"/>
              <path fill-rule="evenodd" clip-rule="evenodd" d="M78.9357 0L77.5761 7.09786L80.0511 10.1745L82 0H78.9357ZM66.0644 0L63 16H66.0656L68.1658 5.03137L77.0192 16H78.9355L79.314 14.0413L67.9806 0H66.0644Z" fill="#F3652B"/>
        </svg>
        </a>
        </div>
         


    </template>
    <template #end>
        <InputText placeholder="Search" type="text" />
        
    </template>
</Menubar>


<!-- Banner App -->
<section class="flex-col p-8">
    <div class="">
        <div class="self-stretch text-gray-700 text-2xl font-normal">Welcome, <span>UserName</span> </div>
        <h1 class="self-stretch text-gray-900 text-4xl font-bold">Build powerful applications using Edge Computing.</h1>
    </div>

    <div class="flex flex-wrap gap-2">
          <Button size="small" label="Create Application" icon="pi pi-plus-circle" iconPos="right"/>
          <Button size="small" label="Documentation" icon="pi pi-book" plain text />
          <Button size="small" label="Azion API" icon="pi pi-code" plain text />
    </div>
</section>


<section class="flex-col gap-4">

  <div class="p-8 flex align-items-center gap-4">
      <div class="text-gray-900 text-xl font-semibold">Real Time Metrics</div>
      <div class="flex gap-2">
      <Button size="small" label="Invite Member" icon="pi pi-chevron-right" plain text iconPos="right" /> </div>
  </div>

  <div class="p-8 flex align-items-center gap-4">
      <div class="text-gray-900 text-xl font-semibold">Real Time Metrics</div>
      <div class="flex gap-2">
      <Button size="small" label="Invite Member" icon="pi pi-chevron-right" plain text iconPos="right" /> </div>
  </div>
</section>


<div class="p-8 flex align-items-center gap-4">
    <div class="text-gray-900 text-xl font-semibold">Teams</div>
    <div class="flex gap-2">
    <Button size="small" label="Invite Member" icon="pi pi-user-plus" plain text iconPos="right" /> </div>
</div>



</template>

<script setup>
import { ref } from 'vue';
import Button from 'primevue/button';
const visibleLeft = ref(false);
const visibleRight = ref(false);
const visibleTop = ref(false);
const visibleBottom = ref(false);

</script>
