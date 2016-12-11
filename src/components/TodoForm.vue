<template>
<form v-on:submit.prevent="addTodo(newTodo)">
            <div class="form-group">
                <div class="form-group">
                    <input type="text" v-model="newTodo.title" class="form-control" placeholder="add todo">
                </div>
            </div>
            <div class="form-group">
                <button class="btn btn-success" type="submit">Add todo</button>
            </div>
        </form>
  
</template>

<script>
export default {
  props: ['todos'],
        data() {
            return {
                newTodo: {
                    id: null,
                    title: '',
                    complete: false
                }
            }
        },
        methods: {
            addTodo: function(newTodo) {
                this.todos.push(newTodo);
                this.newTodo = {
                    id: null,
                    title: '',
                    complete: false,
                };
            },
        }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.complete{
    text-decoration: line-through;
        color: #BDBDBD;
    }
    
    button {
        margin-left: 2px;
    }
</style>
