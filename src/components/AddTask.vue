<template>
    <form @submit.prevent="onSubmit" class="add-form">
        <div class="form-control">
            <label for="">Task</label>
            <input v-model="text" name="text" type="text" placeholder="Add task">
        </div>
        <div class="form-control">
            <label for="">Date & Time</label>
            <input v-model="day" name="day" type="text" placeholder="Add day & time">
        </div>
        <div class="form-control form-control-check">
            <label for="">Set Reminder</label>
            <input v-model="reminder" name="reminder" type="checkbox">
        </div>
        <input type="submit" class="btn btn-block" value="Save task">

    </form>
</template>

<script>
export default {
    name: 'AddTask',
    data() {
        return {
            text: '',
            day: '',
            reminder: false,
        }
    },
    methods: {
        onSubmit(e) {
            e.preventDefault()
            // console.log("submit")

            if (!this.text) {
                alert('Please add a task!')
                return
            }

            const newTask = {
                // id: Math.floor(Math.random() * 100000),
                text: this.text,
                day: this.day,
                reminder: this.reminder
            }

            // console.log(newTask)
            this.$emit('add-task', newTask)

            this.text = ''
            this.day = ''
            this.reminder = false


        }
    }
}
</script>

<style scoped>
.add-form {
    margin-bottom: 40px;
}

.form-control {
    margin: 20px 0
}

.form-control label {
    display: block
}

.form-control input {
    width: 100%;
    height: 40px;
    margin: 5px;
    padding: 3px 7px;
    font-size: 17px;
}

.form-control-check {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.form-control-check label {
    flex: 1;
}

.form-control-check input {
    flex: 2;
    height: 20px;
}
</style>