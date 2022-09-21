<template>
  
  <div
        class="noTasks"
        >
        <v-icon color="primary" size="100px">
            mdi-check
        </v-icon>
           <div class="text-h5 primary--text">No tasks</div>
    </div>
</template>

<style lang="scss" scoped>
    .noTasks {
        display: flex;
        flex-direction: column;
        justify-items: center;
        align-items: center;
        margin-top: 50%;
        opacity: 0.5;
    }
</style>