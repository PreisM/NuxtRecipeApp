<template>
  <section class="recipes">
    <Recipe 
    v-for="recipe in recipes"
    :key="recipe.id"
    :thumbnail="recipe.thumbnail" 
    :title="recipe.title" 
    :previewText="recipe.previewText"
    :id="recipe.id" />
  </section>
</template>


<script>
import Recipe from '@/components/Recipe'

export default {
  components: {
    Recipe
  },
  asyncData() {
    //database
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: "1",
              title: "Delicous pizza",
              previewText: "Awesome Pizza!",
              thumbnail: "https://pizzeriasangiovanni.pl/wp-content/uploads/2019/08/p1.jpg"
            },
            {
              id: "2",
              title: "Delicous shrimps",
              previewText: "Nice shrimps!",
              thumbnail: "https://imagesvc.meredithcorp.io/v3/mm/image?url=https%3A%2F%2Fstatic.onecms.io%2Fwp-content%2Fuploads%2Fsites%2F9%2F2018%2F04%2Fgrilled-gulf-shrimp-with-comeback-sauce-XL-RECIPE0518.jpg&q=85g"
            }
          ]
        })
      }, 1500)
    })
  }
}
</script>
<style scooped>
.recipes {
 display: flex;
 flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}



</style>