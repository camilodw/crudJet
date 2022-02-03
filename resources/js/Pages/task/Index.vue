<template>
  <app-layout>
    <template #header>
      <h2 class="h4 font-weight-bold">Tasks</h2>
    </template>
    <div class="container-fluid">
      <div class="row">
        <div class="col-12 text-center">
          <inertia-link
            :href="route('task.create')"
            class="btn btn-dark"
            type="button">
            Nuevo
          </inertia-link>
        </div>
        <div class="col-12">
          <div class="table-responsive">
            <table class="table">
              <thead>
                <tr>
                  <th scope="col">name</th>
                  <th scope="col">description</th>
                  <th scope="col">status</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="task in tasks" :key="task.id">
                  <td>{{ task.name }}</td>
                  <td>{{ task.description }}</td>
                  <td
                    v-if="task.status == 1"
                    class="alert bg-success form-control text-center text-white">
                    Active
                  </td>
                  <td
                    v-if="task.status == 0"
                    class="alert bg-danger form-control text-center text-white">
                    Disable
                  </td>
                  <td>
                    <inertia-link
                      :href="route('task.edit', task.id)"
                      class="btn btn-warning form-control"
                      type="button">
                      Edit
                    </inertia-link>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </app-layout>
</template>
<script>
import { defineComponent } from "vue";
import AppLayout from "@/Layouts/AppLayout.vue";

export default {
  components: {
    AppLayout,
  },
  props: {
    tasks: Array,
  },
};
</script>

