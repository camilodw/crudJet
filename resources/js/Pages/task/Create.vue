<template>
    <app-layout>
         <template #header>
            <h2 class="h4 font-weight-bold">Create task</h2>
        </template>
        <div class="container-fluid">
            <div class="row justify-content-center">
                <div class="col-lg-6 mt-5">
                    <form @submit.prevent="store">
                        <div class="form-group">
                            <label for="" class="form-label">Name:</label>
                            <input type="text" class="form-control">
                        </div>
                        <div class="form-group">
                            <label for="" class="form-label">Description:</label>
                            <input type="text" class="form-control">
                        </div>
                        <div class="form-group">
                            <label for="" class="form-label">Status:</label>
                            <button class="btn btn-success form-control">Active</button>
                        </div>
                        <div class="text-center mt-4">
                            <button class="btn btn-primary form-control">
                            Save
                        </button>
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

export default(
    {
        name:"create-task",
        components:
        {
            AppLayout
        },
        data(){
            return{
                Task:
                {
                name: "" ,
                description: "",
                status:true
                }
            }
        },
        methods:{
            store(){

            }

        }

    }
);

</script>
