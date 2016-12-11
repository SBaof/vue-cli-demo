<template>
<ul class="list-group">
        <h3>My TODOs <span v-show="remaining">[{{ remaining }}]</span></h3>
            <!-- <li class="list-group-item" v-for="(todo, index) in todos" v-bind:class="todo.complete ? 'complete' : ''"> -->
            <li class="list-group-item" v-for="(todo, index) in todos" v-bind:class="{'complete': todo.complete}">
                {{ todo.title }}
                <button class="btn btn-danger btn-xs pull-right" v-on:click="deleteTodo(index)">Delete</button>
                <button class="btn btn-xs pull-right" v-bind:class="[todo.complete ? 'btn-success' : 'btn-warning']" v-on:click="markDone(todo)">{{ todo.complete ? 'Done' : 'Undo' }}</button>
            </li>
        </ul>
  
</template>

<script>
export default {
    props: ['todos'],
    methods: {
        deleteTodo(index) {
            this.todos.splice(index, 1);
        },
        markDone(todo) {
            todo.complete = !todo.complete;
        }
    },
    computed: {
        remaining() {
            return this.todos.filter(function(todo) {
                return !todo.complete;
            }).length;
        }
    }
} 
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.complete {
    text-decoration: line-through;
        color: #BDBDBD;
    }
    
    button {
        margin-left: 2px;
    }
</style>
