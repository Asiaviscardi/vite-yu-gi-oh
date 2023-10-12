<script>
import axios from 'axios'
export default {
    name:'Main',

    data(){
        return{
            cards:[]
        };
    },

    created(){
        this.fetchCards();
    },

    methods: {
        async fetchCards(){
            try{
                const response = await axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
                    params:{
                        num: 10,
                        offset: 0
                    },
                });

                this.cards = (await response).data.data;
            }catch (error){
                console.error('Errore nella richiesta API', error);
            }
        }

    }

}


</script>

<template>

    <div class="main">

        <div class="card-container">

            <div class="ricerca">found</div>
    
            <div class="card" v-for="card in cards" :key="card.id">

                <img :src="card.card_images[0].image_url" alt="Card Image" />

                <p>{{ card.name }}</p>

            </div>
    
        </div>

    </div>

</template>

<style scoped lang="scss">

.main{
  display: flex;
  justify-content: center;
  .card-container{
      width: 80%;
      background-color: white;
      padding: 20px;
      display: flex;
      flex-wrap: wrap;
      .card{
        width: 20%;
        background-color: #D48F38;
        border: 1px solid black;
        margin-bottom: 15px;

        img{
            width: 100%;
        }

      }

      .ricerca{
        width: 100%;
        background-color: black;
        color: white;
        padding: 10px;
      }
    }
}

</style>