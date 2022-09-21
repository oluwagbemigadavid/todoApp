<template>
    <div class="home ">
        <field-add-task></field-add-task>
        <list-tasks
            v-if="$store.state.tasks.length"
        />
        <NoTask v-else />

    </div>
</template>

<script>
import FieldAddTask from "../components/Todo/FieldAddTask.vue";
import NoTask from "@/components/Todo/NoTask.vue";

export default {
    components: {
    "field-add-task": FieldAddTask,
    //Another way of loading componenets into our vue application!
    "list-tasks": require("../components/Todo/ListTasks.vue").default,
    NoTask
},
}
</script>