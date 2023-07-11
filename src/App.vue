<template>
  <!-- Overlayer Components -->

  <Sidebar v-model:visible="showSideBar"> </Sidebar>

  <Dialog
    position="top"
    v-model:visible="showModal"
    modal
    header="What you looking for?"
    :style="{ width: '50vw' }"
  >
  </Dialog>

  <Dialog
    position="top"
    v-model:visible="showModalCreate"
    modal
    header="New Application"
    :style="{ width: '50vw' }"
  >
  </Dialog>

    <div class="card flex justify-content-center">
        <Button type="button" label="Toggle" @click="toggle" aria-haspopup="true" aria-controls="overlay_menu" />
        <Menu ref="menu" id="overlay_menu" :model="createActions" :popup="true" />
        <Toast />
    </div>


  <header class="bg-gray-800 border-b flex p-4 justify-between bg-black">
    <div class="flex w-full h-none gap-4">
      <Button
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
        <InputText class="w-250px"
          @click="showModal = true"
          v-model="value1"
          placeholder="Quick search for anything | ⌘+k"
        />
      </span>
    </div>

    <div class="flex justify-items-end gap-2">
    <Tag icon="pi pi-check" severity="success" value="Success"></Tag>
      <Button
        raised
        size="small"
        icon="pi pi-plus-circle"
        @click="showModalCreate = true"
      />
      <Button size="small" severity="secondary" icon="pi pi-bell"></Button>
      <Avatar
        shape="circle"
        image="/images/avatar/gab.png"
        v-badge="99"
        size="large"
      />
    </div>
  </header>
  <!-- Banner App -->
  <section class="flex-col p-4">
    <div class="">
      <div class="self-stretch text-gray-200 text-2xl font-normal">
        Welcome, {{ userName }}
      </div>
      <h1 class="self-stretch text-4xl font-bold">
        Build powerful applications using Edge Computing.
      </h1>
    </div>

    <div class="flex flex-wrap gap-2">
      <Button
        raised
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
const userName = ref('userName');

const createActions = ref([
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
    
]);

const toast = useToast();

const toggle = (event) => {
    menu.value.toggle(event);
};



</script>
