<template>
  <section class="single-recipe">
  <!-- <p>{{ $route.params.id }}</p> show the current id -->
  <h1>{{ recipe.title }}</h1>
  <div>
    <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
    <p>
      {{ recipe.description }}
    </p>
  </div>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      // fake DB request
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "Decilius Food",
              previewText: "Mmmm nam nam",
              thumbnail: "https://i.ndtvimg.com/i/2016-06/chinese-625_625x350_81466064119.jpg",
              description: "full description...."
            },
            {
              id: "2",
              title: "Decilius Food2",
              previewText: "Mmmm more nam nam",
              thumbnail: "https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRl3AH90cez9J1ToQO7d4WUdumsRLHIi5jxcvV3F1H8sayagPaM",
              description: "full description...."
            }
          ].find(el => el.id === context.params.id)
        })
      }, 1500)
    })
  }
}
</script>

<style scoped>
  .single-recipe {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
  }
  .recipe-image {
    width: 100%;
  }
</style>
