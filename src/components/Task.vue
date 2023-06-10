<template>
  <div @dblclick="$emit('toggle-reminder',task.id)" :class="[task.reminder ? 'reminder' : '', 'task']">
    <div class="task2">

        <h3>{{ task.text }}</h3>
        <i @click="onDelete(task.id)" class="fa-solid fa-xmark"></i>
    </div>
    <p>{{ task.day }}</p>

  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
  methods:{
    onDelete(id){
       this.$emit('delete-task',id)
    }
  }
};
</script>
<style scope>
.fa-xmark{
    color:red;
}
.task {
    background: #f4f4f4;
    /* color: black; */
    margin:5px;
    padding:10px 20px;
    cursor:pointer;
}
.task.reminder{
    border-left: 5px solid green;
}
.task2{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
/* .task h3 {
    display: flex;
    align-items: center;
    justify-content: space-between;
} */
</style>
