<template>
  <v-list
        flat
        class="pt-0"
        >
        <TaskComp 
        v-for="task in $store.state.tasks" 
        :key="task.id" 
        :task="task"
        />
            
        </v-list>
</template>

<script>
import TaskComp from './TaskComp.vue';
export default {
    components: { TaskComp }
}
</script>