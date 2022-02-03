<template>
    <app-layout>
         <template #header>
      <h2 class="h4 font-weight-bold">Edit task</h2>
    </template>
    </app-layout>
</template>
<script>

import { defineComponent } from "vue";
import AppLayout from "@/Layouts/AppLayout.vue";

export default(
    {
        components:
        {
            AppLayout
        }
    }
);

</script>
