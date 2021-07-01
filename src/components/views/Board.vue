<template>
    <section>
        <h3><span>Mis paneles</span> > {{name}}</h3>
        <input 
        type="text"
        placeholder="Añade una lista"
        v-model="listName"
        @keyup.enter="add()"
        >
        <div class="container">
            <column 
                v-for="(list, index) in boardList"
                :key="index"
                :listId="list.id"
                :name="list.name"
                >
            </column>
        </div>
    </section>
</template>

<script>
import Column from '@/components/Column'
export default {
    name: 'board-view',
    components: {Column},
    props:{
        name:String,
        id:String
    },
    data(){
        return{
            listName:'',
            boardList:[
                {id:'1',name:'Todo'},
                {id:'2',name:'Doing'}
            ]
        }
    },
    methods:{
        add(){
            this.boardList.push({name:this.listName})
        }
    }
}
</script>

<style scoped>

    .container{
        width: ;
    }

    section{
        display: flex;
        justify-content: center;
        flex-direction: column;
        text-align: left;
        width: 100%;
        margin: 0px;
    }

    h3{
        color: #37474f;
        text-align: left;
        margin: 1.5rem;
    }

    input{
        box-sizing: border-box;
        background-color: #546E7A;
        border: 2px solid #546E7A;
        border-radius: 3px;
        font-size: 1.1rem;
        outline: 0;
        padding: 0.5rem;
        margin: 10px 0px 10px 0px;
        transition: all 600ms ease;
    }

    input:focus{
        background-color: white;
        color: #546E7A;
    }

    input:active{
        background-color: white;
        color: #546E7A;
    }

    input::placeholder{
       color:white;
    }

    input:active::placeholder{
        color: #546E7A;
    }

</style>