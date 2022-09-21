<template>
    <div>
           <v-menu
        bottom
        left
        >
        <template v-slot:activator="{ on, attrs }">
            <v-btn
            light
            color="primary"
            icon
            v-bind="attrs"
            v-on="on"
            >
            <v-icon>mdi-dots-vertical</v-icon>
            </v-btn>
        </template>

        <v-list>
            <v-list-item
                v-for="(item, index) in items"
                :key="index"
                @click="handleClick(index)"
                >
                <v-list-item-icon>
                    <v-icon v-text="item.icon"></v-icon>
                </v-list-item-icon>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item>
        </v-list>
    </v-menu>
    
    <DeleteDialouge 
    v-if="dialogues.delete" 
    :task="task"
    @close="dialogues.delete = false"
    />
    <EditDialogue 
    v-if="dialogues.edit" 
    :task="task"
    @close="dialogues.edit = false"    
    />
    </div>
 
</template>

<script>
import DeleteDialouge from "./Dialogs/DeleteDialouge.vue";
import EditDialogue from "./Dialogs/EditDialogue.vue";
export default {
    props: ['task'],
    components: {  EditDialogue, DeleteDialouge, },
    data: () => ({
        dialogues: {
            delete: false,
            edit: false
        },
        items: [
            { title: 'Edit', icon: 'mdi-pencil', click() {this.dialogues.edit = true} },
            { title: 'Due Date', icon: 'mdi-calendar', click() {} },
            { title: 'Delete', icon: 'mdi-delete', click() {this.dialogues.delete = true} },
         ],
    }),
    methods: {
        handleClick(index) {
            this.items[index].click.call(this)
        }
    }
}
</script>

<style>

</style>