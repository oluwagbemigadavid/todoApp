<template>
   <v-text-field
        class="pa-3"
        hide-details
        v-model="newTaskTitle"
        @keyup.enter="addTask()"
        outlined
        label="Add Taks..."
        clearable
        >
            <template v-slot:append>
               <v-icon
               @click="addTask()"
               color="primary"
               :disabled="newTaskTitleInvalid"
               >
               mdi-plus
            </v-icon>
            </template>
        </v-text-field>
</template>

<script>
export default {

    data() {
        return {
            newTaskTitle: "",
        };
    },
    computed: {
      newTaskTitleInvalid () {
        return !this.newTaskTitle
      }
    },
    methods: {
        addTask() {
            if(!this.newTaskTitleInvalid){
                this.$store.dispatch("addTask", this.newTaskTitle);
                this.newTaskTitle = "";
            }
        },
    },
}
</script>
