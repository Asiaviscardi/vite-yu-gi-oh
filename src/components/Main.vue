<script>
export default {
    name:'Main'

}
</script>

<template>

    <div class="main">

        <div class="card-container">
    
            <div class="card">card</div>
            <div class="card">card</div>
            <div class="card">card</div>
            <div class="card">card</div>
            <div class="card">card</div>

            <div class="card">card</div>
            <div class="card">card</div>
            <div class="card">card</div>
            <div class="card">card</div>
            <div class="card">card</div>
    
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

      }
    }
}


</style>