<template>
    <section>
        <header>
            <h3>{{name}}</h3>
        </header>
        <task-list
            :listId="listId"
            :tasks="tasksList">    
        </task-list>
    </section>
</template>

<script>
import TaskList from './TaskList'

export default {
    name:'column',
    components:{TaskList},
    props:{
        listId: String,
        name: String
    },
    data(){
        return{
            tasksList: [
                {id:'1',title:'Aprender Vue',completed:false},
                {id:'2',title:'Aprender Vuex',completed:false}
            ]
        }
    }
}
</script>

<style>
    section{
        box-sizing: border-box;
        border-radius: 3px;
        box-shadow: 0 0 0 0.5px rgba(49,49,93,.03),
            0 2px 5px 0 rgba(49,49,93,.1),
            0 1px 2px 0 rgba(0,0,0,.08);
        margin: 12rem;
        padding: 1rem;
        width: 33%;
    }   

    header{
        color: #37474f;
        padding-bottom: 1rem;
    }

    h3{
        margin: 0;
    }
</style> 