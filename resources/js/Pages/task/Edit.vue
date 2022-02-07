<template>
  <app-layout>
    <template #header>
      <h2 class="h4 font-weight-bold">Edit task</h2>
    </template>
    <div class="container-fluid">
      <div class="row justify-content-center">
        <div class="col-lg-6 mt-5">
          <form @submit.prevent="update">
            <div class="form-group">
              <label for="" class="form-label">Name:</label>
              <input type="text" class="form-control" v-model="Task.name" />
            </div>
            <div class="form-group">
              <label for="" class="form-label">Description:</label>
              <input
                type="text"
                class="form-control"
                v-model="Task.description"
              />
            </div>
            <div class="form-group">
              <label for="" class="form-label">Status:</label>
              <button
                class="btn btn-success form-control"
                v-if="Task.status == true"
                type="button"
                v-on:click="toggleStatus"
              >
                Enabled
              </button>
              <button
                class="btn btn-danger form-control"
                v-if="Task.status == false"
                type="button"
                v-on:click="toggleStatus"
              >
                Disabled
              </button>
            </div>
            <div class="text-center mt-4">
              <button class="btn btn-primary form-control">Save</button>
                <inertia-link
                                method="delete"
                                :href="route('task.destroy', task.id)"
                                class="btn btn-danger form-control" type="button">
                                Delete
                </inertia-link>
            </div>
          </form>
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
  props: [ "task" ],
  data() {

    return {
      Task:
      {
        description: this.$props.task.description,
        name: this.$props.task.name,
        status:this.$props.task.status
      },
    };

  },
 methods:
 {
     toggleStatus()
     {
          this.Task.status = !this.Task.status;
     },

    update()
    {
      this.$inertia.put(
        route( "task.update" , this.$props.task.id ),
        this.Task
      );
    },
 }
};
</script>
