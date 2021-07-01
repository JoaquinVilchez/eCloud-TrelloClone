<template>
    <div>
        <h3>Mis paneles</h3>
        <div class="boards-collection">
            <input 
            type="text"
            placeholder="Añade un nuevo panel"
            v-model="boardName"
            @keyup.enter="add"
            />
            <board-card
                v-for="(board, index) in boards"
                :key="index"
                :name="board.name"
                :id="board.id"
            ></board-card>
        </div>
    </div>
</template>

<script>
import BoardCard from '@/components/BoardCard'

export default {
  name: 'home-view',
  components: {BoardCard},
  data(){
      return {
        boardName: '',
        boards:[
            {id: '1', name:'Tareas'},
            {id: '2', name:'Lista de la compra'}
        ]
      }
  },
  methods:{
      add(){
          this.boards.push({name:this.boardName})
          this.boardName=''
      }
  }
}
</script>

<style scoped>
    h3{
        text-align: center;
        margin: 1.5rem;
    }

    .boards-collection{
         display: flex;
         flex-direction: column;
         flex-wrap: wrap;
         justify-content: center;
         align-items: center;
         padding-top: 1rem;
         padding: 0px 10%;
    }

    input{
        box-sizing: border-box;
        background-color: #546E7A;
        border: 2px solid #546E7A;
        border-radius: 3px;
        font-size: 1.1rem;
        outline: 0;
        padding: 0.5rem;
        transition: all 600ms ease;
        width: 50%;
        margin-bottom: 40px;
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
</style>