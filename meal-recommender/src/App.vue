<script>
    import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
    import { library } from '@fortawesome/fontawesome-svg-core';
    import { faCoffee,faPlus,faMinus } from '@fortawesome/free-solid-svg-icons';
    import RecipeLayout from './RecipeLayout.vue';
    import axios from "axios"

    library.add(faCoffee,faPlus,faMinus)

    export default{
        components:{
            FontAwesomeIcon,
            'RecipeLayout':RecipeLayout,
        },
        data(){
            return{
                ingredients:[""]
            }
        },
        methods:{
            addIngredient(){
                this.ingredients.push("")
            },
            removeIngredints(index){
                this.ingredients.splice(index,1)
            },
            onChange(index,value){
                this.ingredients[index] = value
            },
            async recommedRecipes(){
                const data = {"ingredients":this.ingredients}
                console.log(data,"DATA")
                const response = await axios.post("http://127.0.0.1:5000/predict",data)
                console.log(response.data)
            }
        }
    }
</script>

<template>
    <div class="recommender-area">
        <div class="recommender-title">
            <p>Add Your Ingredients</p>
        </div>
        <div class="ingredients">
            <div class="inputs-section">
                <div v-for="(ingredients,index) in ingredients" :key="index" class="ing-input">
                    <div class="remove" @click="removeIngredints(index)">
                        <font-awesome-icon :icon="['fa', 'minus']"  style="color: #fff;"/>
                    </div>
                    <input type="text" placeholder="Add Ingredient" @change="onChange(index,$event.target.value)">
                </div>
            </div>
            <div class="add-input" @click="addIngredient()">
                <font-awesome-icon :icon="['fa', 'plus']"  style="color: #000;"/>
            </div>
        </div> 
        <div class="recommend-recipes" @click="recommedRecipes()">
            <a href="#">Recommend Recipes</a>
        </div>
    </div>
    <div class="recipes">
        <RecipeLayout/>
    </div>

</template>

<style scoped>
    .recommender-area{
        margin: 20px 0;
        background-color: #302f2f6b;
        min-height: 200px;
        padding: 10px 40px;
        border-radius: 20px;
    }
    .recommender-title{
        margin: 20px 0;
    }

    .ingredients{
        display: flex;
        align-items: center;
    }

    .ing-input{
        background-color: #1a1818;
        padding: 13px 15px;
        border-radius: 5px;
        margin-right: 5px;
        position: relative;
        transition: 0.5s;
    }
    
    
    .ing-input input{
        background-color: transparent;
        outline: none;
        border: none;
        color: #fff;
    }

    .remove{
        position: absolute;
        top: 7px;
        right: 7px;
        background-color: #302f2f6b;
        width: 20px;
        height: 20px;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        opacity: 0;
        
    }

    .ing-input:hover .remove{
        opacity: 1;
    }

    .inputs-section{
        display: flex;
        align-items: center;
    }
    .add-input{
        padding: 13px 20px;
        background-color: #fff;
        border-radius: 5px;
        transition: 0.5s;
    }

    .add-input:hover{
        cursor: pointer;
        transform: scale(1.03);
    }

    .recipes{
        margin-top: 30px;
    }

    .recommend-recipes{
        background-color: #292828;
        padding: 10px 20px;
        border-radius: 5px;
        width: 200px;
        height: 50px;
        margin: 10px 0;
        text-align: center;
        align-items: center;
        display: flex;
        cursor: pointer;
        transition: 0.5s;
    }
    .recommend-recipes:hover{
        background-color: #383636;
    }
    .recommend-recipes a{
        color: #fff;
        text-decoration: none;
    }

</style>