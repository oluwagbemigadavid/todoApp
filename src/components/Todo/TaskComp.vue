<template>
  
  <div class="tasks" >
            <v-list-item 
            @click="$store.commit('doneTask', task.id)"
            :class="{'green lighten-5' : task.done }"
            >
                <template v-slot:default>
                    <v-list-item-action>
                    <v-checkbox
                        :input-value="task.done"
                        color="primary"
                    ></v-checkbox>
                    </v-list-item-action>

                    <v-list-item-content
                        :class="{'text-decoration-line-through' : task.done }">
                    <v-list-item-title
                    >
                       
                    Task: {{ task.id }}
                    </v-list-item-title> 
                        {{ task.title }}
                    </v-list-item-content>   
                    <v-list-item-action>
                        <TaskMenu :task="task" />
                    </v-list-item-action>
                </template>
            </v-list-item>

            <v-divider></v-divider>

        </div>
</template>

<script>
import TaskMenu from "./TaskMenu.vue";
export default {
    props: ["task"],
    components: { TaskMenu },
}
</script>
