<script setup lang="ts">
defineProps<{
    recipe:any
}>()

const parseNER = (ner_tag:any) =>{
    return JSON.parse(ner_tag.replace(/'/g, '"'))
}
</script>

<template>
    <div class="recommendations">
        <div class="recipes">
            <div class="recommendations-layout">
                <div class="recipe-image">
                    <img src="https://images.immediate.co.uk/production/volatile/sites/30/2020/08/chorizo-mozarella-gnocchi-bake-cropped-9ab73a3.jpg?quality=90&resize=556,505" alt="">
                </div>
                <div class="recipe-description">
                    <h3>{{recipe["title"]}}</h3>
                    <div class="ingredients">
                        <div v-for="(ingredient, index) in JSON.parse(recipe.ingredients)" :key="index">
                            <p>{{ingredient}}</p>
                        </div>
                    </div>
                    <!-- <div class="requirements">
                        <p>Requirements</p>
                        <div class="requirements-ing">
                            <div  v-for="(ner, index) in parseNER(recipe.NER)" :key="index" class="ing-bg">
                                <p>{{ner}}</p>
                            </div>
                        </div>
                    </div> -->
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .recommendations-layout{
        background-color: #302f2f6b;
        border-radius: 10px;
        padding: 25px;
        margin: 15px 5px;
        display: flex;
        align-items: center;

    }
    .recipe-image img{
        width: 210px;
        height: 210px;
        border-radius: 10px;
        object-fit: cover;
    }
    .recipe-description{
        margin: 10px 30px;
        width: 268px;
        min-height: 210px;
    }
    .recipe-description h3{
        font-size: 25px;
        max-width: 210px;
    }
    .ingredients{
        margin-top: 10px;
    }
    .ingredients p{
        margin-top: 5px;
    }
    .requirements{
        margin-top: 10px;
    }

    .requirements-ing{
        display: flex;
        flex-wrap: wrap;
    }
    .ing-bg{
        background-color: #302f2f6b;
        padding: 10px 15px;
        margin-right: 5px;
        border-radius: 10px;
    }

    @media screen and (max-width:500px) {
        .recommendations-layout{
           flex-direction: column;
           max-width: 300px;
        }
        .recipe-description{
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .ingredients p{
            text-align: center;
        }
    }
</style>