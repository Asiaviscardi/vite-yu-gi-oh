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
                        num: 39,
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

            <div class="ricerca">found 39 cards</div>
    
            <div class="card" v-for="card in cards" :key="card.id">

                <img :src="card.card_images[0].image_url" alt="Card Image" />

                <h4>{{ card.name }}</h4>

                <p>{{ card.archetype }}</p>

            </div>
    
        </div>

    </div>

</template>

<style scoped lang="scss">

.main{
  display: flex;
  justify-content: center;
  .card-container{
      width: 90%;
      background-color: white;
      padding: 20px;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      .card{
        width: 15%;
        background-color: #D48F38;
        margin: 0px 25px 15px 25px;

        img{
            width: 100%;
        }

        h4{
            padding: 10px;
            color: white;
            text-align: center;
        }

        p{
            text-align: center;
            padding-bottom: 10px;
        }

      }

      .ricerca{
        width: 92%;
        background-color: black;
        color: white;
        padding: 10px;
      }
    }
}

</style>