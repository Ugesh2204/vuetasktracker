<template>
    <!-- #region -->
     <!-- use a tenary v bind for class add a reminder class if it true -->
     <!--<div :class="[task.reminder ? 'reminder': '', 'task']">-->
    <!-- #endregion -->
    <div 
     @dblclick="$emit('toggle-reminder', task.id)"
     :class="[task.reminder ? 'reminder': '', 'task']">
        <h3>{{ task.text }}
        <i @click="$emit('delete-task',id)" class="fas fa-times"></i>
        </h3>
        <p>{{ task.day}}</p>
    </div>
   
</template>

<script>
export default {
    name: 'Task',
    props: {
        task: Object
    },
    // methods: {
    //     onDelete(id){
    //         //#region
    //         //How to Emit Custom Events in Vue
    //         //Many Vue patterns involve passing data from a parent 
    //         //component to its children using props. But what if we need a child to affect its parent?
    //         //https://learnvue.co/tutorials/vue-emit-guide
    //             //$emit 
    //         //#endregion
    //       this.$emit('delete-task',id)
    //     }
    // }
}
</script>

<style scope>
    .fas {
      color: red;
    }
    .task {
      background: #f4f4f4;
      margin: 5px;
      padding: 10px 20px;
      cursor: pointer;
    }
    .task.reminder {
      border-left: 5px solid green;
    }
    .task h3 {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    </style>