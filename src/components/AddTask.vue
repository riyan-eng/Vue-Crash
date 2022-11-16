<template>
    <div class="form-control">
        <label for="">Task</label>
        <input v-model="task" type="text">
        {{task}}
    </div>
    <div class="form-control">
        <label for="">Date & Time</label>
        <input v-model="day" type="text">
        {{day}}
    </div>
    <div class="form-control">
        <label for="">Set Reminder</label>
        <input v-model="reminder" type="checkbox">
        {{reminder}}
    </div>
    <input type="submit" value="Save task">
</template>

<script>
export default {
    name: 'AddTask',
    data(){
        return{
            task: '',
            day: '',
            reminder: false,
        }
    }
}
</script>