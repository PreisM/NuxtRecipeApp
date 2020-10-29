<template>
  <section class="single-recipe">
    <h1>{{ recipe.title}}</h1>
    <div> 
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p> {{ recipe.descriptionText }}</p>
  </section>
</template>
<script>
export default {
  asyncData(context) {
    //database
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "Delicous pizza",
              previewText: "Awesome Pizza!",
              descriptionText: "This is pizza",
              thumbnail: "https://pizzeriasangiovanni.pl/wp-content/uploads/2019/08/p1.jpg"
            },
            {
              id: "2",
              title: "Delicous shrimps",
              previewText: "Nice shrimps!",
              descriptionText: "This are shrimps",
              thumbnail: "https://imagesvc.meredithcorp.io/v3/mm/image?url=https%3A%2F%2Fstatic.onecms.io%2Fwp-content%2Fuploads%2Fsites%2F9%2F2018%2F04%2Fgrilled-gulf-shrimp-with-comeback-sauce-XL-RECIPE0518.jpg&q=85g"
            }
          ].find(el => el.id === context.params.id)
        })
      }, 1500)
    })
  }
}

</script>
<style scooped>
.single-recipe{
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}
.recipe-image {
  width: 100%;
  height: 300px;
}
</style>