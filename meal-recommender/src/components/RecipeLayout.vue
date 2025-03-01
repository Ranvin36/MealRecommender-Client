<script>

    export default{
        name:'RecipeLayout'
    }
</script>

<template>
    <div class="recommendations">
        <div class="title">
            <h2>Recommended Recipes</h2>
        </div>
        <div class="recipes">

            <div class="recommendations-layout">
                <div class="recipe-image">
                    <img src="https://images.immediate.co.uk/production/volatile/sites/30/2020/08/chorizo-mozarella-gnocchi-bake-cropped-9ab73a3.jpg?quality=90&resize=556,505" alt="">
                </div>
                <div class="recipe-description">
                    <h3>Chicken Curry</h3>
                    <div class="ingredients">
                        <p>1 c. firmly packed brown sugar</p>
                        <p>1 small jar chipped beef, cut up</p>
                        <p>1 large whole chicken", "2 (10 1/2 oz.)</p>
                    </div>
                </div>
            </div>
            <div class="recommendations-layout">
                <div class="recipe-image">
                    <img src="https://images.immediate.co.uk/production/volatile/sites/30/2020/08/chorizo-mozarella-gnocchi-bake-cropped-9ab73a3.jpg?quality=90&resize=556,505" alt="">
                </div>
                <div class="recipe-description">
                    <h3>Chicken Curry</h3>
                    <div class="ingredients">
                        <p>1 c. firmly packed brown sugar</p>
                        <p>1 small jar chipped beef, cut up</p>
                        <p>1 large whole chicken", "2 (10 1/2 oz.)</p>
                    </div>
                </div>
            </div>
            <div class="recommendations-layout">
                <div class="recipe-image">
                    <img src="https://images.immediate.co.uk/production/volatile/sites/30/2020/08/chorizo-mozarella-gnocchi-bake-cropped-9ab73a3.jpg?quality=90&resize=556,505" alt="">
                </div>
                <div class="recipe-description">
                    <h3>Chicken Curry</h3>
                    <div class="ingredients">
                        <p>1 c. firmly packed brown sugar</p>
                        <p>1 small jar chipped beef, cut up</p>
                        <p>1 large whole chicken", "2 (10 1/2 oz.)</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .recipes{
        display: flex;
    }
    .recommendations-layout{
        background-color: #302f2f6b;
        border-radius: 10px;
        padding: 25px;
        margin: 15px 5px;
        display: flex;
    }

    .title h2{
        font-size: 20px;    
    }
    .recipe-image img{
        width: 250px;
        height: 250px;
        border-radius: 10px;
        object-fit: cover;
    }
    .recipe-description{
        margin: 20px 30px;
    }
    .recipe-description h3{
        font-size: 25px;
    }
    .ingredients{
        margin-top: 10px;
    }
    .ingredients p{
        margin-top: 5px;
    }
</style>