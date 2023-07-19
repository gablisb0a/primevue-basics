<template>
  <!-- Overlayer Components -->

  <!-- Product Navigation  -->
  
  <Sidebar v-model:visible="showSideBar"> 
  
 
        <Menu :model="items" />
        <Toast />
 
  
  </Sidebar>
  <Sidebar v-model:visible="showAccountPanel" position="right" > </Sidebar>

<!-- Quick Search -->

  <Dialog
    position="top"
    v-model:visible="showModal"
    modal
    header="What you looking for?"
    :style="{ width: '75vw' }"
  >

  <div class="flex-col col-gap-4">
      <Listbox v-model="selectedCity" :options="actions" filter optionLabel="name" class="w-full" />
  </div>
  </Dialog>


<!--  Modal Create  -->
  <Dialog
    position="top"
    v-model:visible="showModalCreate"
    modal
    header="New Application"
    :style="{ width: '80vw' }"
  >


  </Dialog>


<Menubar>
    <template #start>
        <div class="flex h-auto  h-none gap-4">
      <Button
        plain text
        size="small"
        severity="secondary"
        icon="pi pi-bars"
        @click="showSideBar = true"
      />

      <a
        style="align-self: center"
        class="flex items-center self-center"
        href=""
      >
        <svg
          width="82"
          height="16"
          viewBox="0 0 82 16"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M16.6613 0L0.447256 13.6503L0 16H2.33599L14.8958 5.43151L12.8713 16H15.9351L19 0H16.6613Z"
            fill="#F3652B"
          />
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M22.0645 0L21.4854 3.02307H32.0678L19.4534 13.6444L19 16H34.9355L35.5146 12.9769H24.9323L37.5495 2.3533L38 0H22.0645Z"
            fill="#F3652B"
          />
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M41.0003 0L38 16H40.9997L44 0H41.0003Z"
            fill="#F3652B"
          />
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M47.0644 0L44 16H59.9356L63 0H47.0644ZM49.5536 3.02291H59.3487L57.4422 12.9769H47.6472L49.5536 3.02291Z"
            fill="#F3652B"
          />
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M78.9357 0L77.5761 7.09786L80.0511 10.1745L82 0H78.9357ZM66.0644 0L63 16H66.0656L68.1658 5.03137L77.0192 16H78.9355L79.314 14.0413L67.9806 0H66.0644Z"
            fill="#F3652B"
          />
        </svg>
      </a>

      <span class=" p-input-icon-left">
        <i class="pi pi-search" />
        <InputText 
          style= "width: 440px"
          class=""
          @click="showModal = true"
          v-model="value1"
          placeholder="Quick search for anything | ⌘+k"
        />
       

      </span>
    </div>
    </template>
    <template #end>
        <div class="flex justify-items-end gap-2">
    
        <Tag icon="pi pi-check" severity="success" value="Success"></Tag>
          <Button
            @click="showModalCreate = true"
            raised
            size="small"
            icon="pi pi-plus-circle"
            
          />
          
          <Divider layout="vertical"/>
          <Button plain text size="small" severity="secondary" icon="pi pi-bell"></Button>
          <Button plain text size="small" severity="secondary" icon="pi pi-question-circle"></Button>
          
          <Avatar 
            
            @click="showAccountPanel = true"
            shape="circle"
            image="/images/avatar/gab.png"
            v-badge="99"
            size="large"
          />
    </div>
    </template>


  <header class="bg-gray-900 flex py-4 px-4 justify-between">
   

    
  </header>
</MenuBar>


<!-- Main Content -->
<div class="flex-col gap-8">

<div class="p-4 flex gap-3">

        <div class="flex-col">
            <h2> Headline 2 </h2> 
            <p class="m-0">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Inventore sed consequuntur error repudiandae numquam deserunt quisquam repellat libero asperiores earum nam nobis, culpa ratione quam perferendis esse, cupiditate neque
                quas!
            </p>
        </div>

<Card>
    <template #title> Card</template>
    <template #content>
        <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Inventore sed consequuntur error repudiandae numquam deserunt quisquam repellat libero asperiores earum nam nobis, culpa ratione quam perferendis esse, cupiditate neque
            quas!
        </p>
    </template>

    <template #footer> 
      <Button
        raised
        @click="showModalCreate = true"
        size="small"
        label="Create Application"
        icon="pi pi-plus-circle"
        iconPos="right"
      />
    
    </template>
</Card>




</div>








  <!-- Banner App -->
  <section class="flex-col p-4">
    <div class="">
      <div class="self-stretch text-white text-2xl font-normal">
        Welcome, {{ userName }}
      </div>
      <h1 class="self-stretch text-4xl font-bold">
        Build powerful applications using Edge Computing.
      </h1>
    </div>

    <div class="flex flex-wrap gap-2">
      <Button
        raised
        @click="showModalCreate = true"
        size="small"
        label="Create Application"
        icon="pi pi-plus-circle"
        iconPos="right"
      />
      <Button size="small" label="Documentation" icon="pi pi-book" plain text />
      <Button size="small" label="Azion API" icon="pi pi-code" plain text />
    </div>
  </section>

  <!-- Section Metrics -->
  <section class="flex-col gap-4">
    <div class="p-4 flex align-items-center gap-4">
      <div class="border-round p-3 bg-gray-800">
        <i class="pi pi-chart-line"></i>
      </div>
      <div class="text-white text-xl font-semibold">Real Time Metrics</div>

      <Button
        size="small"
        label="See all Dashbords"
        icon="pi pi-chevron-right"
        plain
        text
        iconPos="right"
      />
    </div>

    <!-- Card Basic -->

    <div class="flex gap-4 px-4">
        
        <div style="height: 160px" class="w-full flex-col bg-gray-800 gap-2 p-4 shadow-2 border-round">
     
        </div>

        <div style="height: 160px" class="w-full flex-col bg-gray-800 gap-2 p-4 shadow-2 border-round">
           
        </div>

        <div style="height: 160px" class="w-full flex-col bg-gray-800 gap-2 p-4 shadow-2 border-round">
        
        </div>
    </div>

    
    
  </section>




  <!-- Section Teams -->
  <div class="p-4 flex align-items-center gap-4">
    <div class="border-round p-3 bg-gray-800">
        <i class="pi pi-users"></i>
      </div>
    <div class="text-xl font-semibold">Teams</div>
    <div class="flex gap-2">
      <Button
        size="small"
        label="Invite Member"
        icon="pi pi-user-plus"
        plain
        text
        iconPos="right"
      />
    </div>
  </div>

  <div class="flex gap-4 px-4">
        
        <div style="height: 160px" class="w-full flex-col bg-gray-800 gap-2 p-4 shadow-2 border-round">
     
        </div>

        <div style="height: 160px" class="w-full flex-col bg-gray-800 gap-2 p-4 shadow-2 border-round">
           
        </div>

        <div style="height: 160px" class="w-full flex-col bg-gray-800 gap-2 p-4 shadow-2 border-round">
        
        </div>
    </div>

<!-- Template List Teams -->

<div class="flex  flex-col gap-4 p-4">
    
</div>


</div>


</template>


<!-- JS   -->
<script setup>
// Imports
import { ref } from 'vue';
import Button from 'primevue/button';

// Variables
const showSideBar = ref(false);
const showModal = ref(false);
const showModalCreate = ref(false);
const showAccountPanel = ref(false);
const userName = ref('userName');

const selectedCity = ref();
const actions = ref([
    { name: 'Create new Application', code: 'NY' },
    { name: 'My Applications', code: 'RM' },
    { name: 'Dashboards and Metrics', code: 'LDN' },
    { name: 'Account Settings', code: 'IST' },
    { name: 'Marketplace', code: 'IST' },
]);


const items = ref([
    {
        label: 'Options',
        items: [
            {
                label: 'Update',
                icon: 'pi pi-refresh',
                command: () => {
                    toast.add({ severity: 'success', summary: 'Updated', detail: 'Data Updated', life: 3000 });
                }
            },
            {
                label: 'Delete',
                icon: 'pi pi-times',
                command: () => {
                    toast.add({ severity: 'warn', summary: 'Delete', detail: 'Data Deleted', life: 3000 });
                }
            }
        ]
    },
    {
        label: 'Navigate',
        items: [
            {
                label: 'Vue Website',
                icon: 'pi pi-external-link',
                url: 'https://vuejs.org/'
            },
            {
                label: 'Router',
                icon: 'pi pi-upload',
                to: '/fileupload'
            }
        ]
    }
]);


</script>
