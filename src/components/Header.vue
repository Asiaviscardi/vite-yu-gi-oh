<script>
export default {
    name:'Header'

}
</script>

<template>

    <div class="logo-container">

        <h1>Yu-Gi-OH Api</h1>

    </div>

    <div class="option-container">

        <select name="" id="">

            <option value="">categoria 1</option>

            <option value="">categoria 2</option>

            <option value="">categoria 3</option>

            <option value="">categoria 4</option>

        </select>
        
    </div>
  
</template>

<style scoped lang="scss">

.logo-container{
    width: 100%;
    background-color: white;
    margin-bottom: 20px;
    padding-left: 20px;
}

.option-container{
    margin-left: 5%;
    margin-bottom: 10px;

}

select{
    width: 130px;
    border-radius: 5%;
    padding: 10px;
    border: none;
    
}
</style>