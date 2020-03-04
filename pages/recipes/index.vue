<template>
    <section class="recipes">
        <Recipe v-for="recipe in recipes"
          :key="recipe.id"
          :thumbnail="recipe.thumbnail"
          :title="recipe.title"
          :previewText="recipe.previewText"
          :id="recipe.id"
        />
    </section>
</template>

<script>
import Recipe from '@/components/Recipe'

export default {
  components: {
      Recipe
  },
  asyncData() {
    return new Promise((resolve, reject) => {
      // fake DB request
      setTimeout(() => {
        resolve({
          recipes: [
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
          ]
        })
      }, 1500)
    })
  }
}
</script>

<style scope>
.recipes {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}
</style>
