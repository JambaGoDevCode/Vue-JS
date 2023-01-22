<template>
  <form @submit.prevent="addRecipe">
    <div>
      <label>name</label>
      <input v-model="recipe.name" />
    </div>

    <div>
      <label>ingredients</label>
      <textarea
        name=""
        id=""
        cols="30"
        rows="10"
        v-model="recipe.ingredients"
      ></textarea>
    </div>

    <div>
      <label>steps</label>
      <textarea v-model="recipe.steps"></textarea>
    </div>
    <button type="submit">Add recipe</button>
  </form>
</template>

<script>
import { v4 as uuidv4} from "uuid";

export default{
  name: "App",
  data(){
    return{
      recipe:{
        name:"",
        ingredients:"",
        steps:"",
      },recipes: [],
    };
  },

  computed:{
    formValid(){
      const { name, ingredients, steps} = this.recipe;
      return name && ingredients && steps;
    },
  },
  
  methods:{
    addRecipe(){
      if(!this.formValid){
        return;
      }
      this.recipes.push({
        id: uuidv4(),
        ...this.recipe,
      });
    },
    deleteRecipe(index){
      this.recipes.splice(index,1);
    },
  },
};

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.content{
  white-space: pre-wrap;
}
</style>
