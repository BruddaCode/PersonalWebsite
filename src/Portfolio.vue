<script setup>
const imageUrl = (path) => new URL(`../media/portfolio/${path}`, import.meta.url).href

const projects = [
  {
    title: "Self Driving Challenge",
    description: "Cool filler text that serves no real purpose but is here to fill space and make the website look more complete and less empty.",
    images: [
        {
      src: imageUrl("SDC1.jpg"),
            alt: "Self Driving Challenge Screenshot 1",
            width: "100%",
        },
        {
      src: imageUrl("SDC2.png"),
            alt: "Self Driving Challenge Screenshot 2",
            width: "100%",
        }
    ]
  },
  {
    title: "Localisatie van schepen in de haven",
    description: "Cool filler text that serves no real purpose but is here to fill space and make the website look more complete and less empty.",
    images: [
        {
        src: imageUrl("Tidalis1.png"),
            alt: "Tidalis Screenshot 1",
            width: "100%",
        },
        {
        src: imageUrl("Tidalis2.png"),
            alt: "Tidalis Screenshot 2",
            width: "100%",
        },
        {
        src: imageUrl("Tidalis3.png"),
            alt: "Tidalis Screenshot 3",
            width: "100%",
        }
    ]
  },
  {
    title: "ATM",
    description: "Cool filler text that serves no real purpose but is here to fill space and make the website look more complete and less empty.",
    images: [
        {
        src: imageUrl("ATM.jpg"),
            alt: "ATM Screenshot",
            width: "80%",
        }
    ]
  },
  {
    title: "Stoplight",
    description: "Cool filler text that serves no real purpose but is here to fill space and make the website look more complete and less empty.",
    images: [
      {
        src: imageUrl("StopLight.jpg"),
        alt: "Stoplight Screenshot",
        width: "50%",
      }
    ]
  },
  {
    title: "ACM",
    description: "Cool filler text that serves no real purpose but is here to fill space and make the website look more complete and less empty.",
    images: [
      {
        src: imageUrl("ACM.png"),
        alt: "ACM Screenshot",
        width: "80%",
      }
    ]
  },
  {
    title: "Lift",
    description: "Cool filler text that serves no real purpose but is here to fill space and make the website look more complete and less empty.",
    images: [
      {
        src: imageUrl("Lift.png"),
        alt: "Lift Screenshot",
        width: "40%",
      }
    ]
  }
]
</script>

<template>
    <br>
    <div
        v-for="(project, index) in projects"
        :key="project.title"
        :class="index % 2 === 0 ? 'portfolio-item' : 'portfolio-item-flipped'"
    >
        <div class="portfolio-text">
            <h2>{{ project.title }}</h2>
            <p>{{ project.description }}</p>
        </div>

        <div class="portfolio-img-container">
            <img
                v-for="image in project.images"
                :key="image.src"
                class="portfolio-img"
                :src="image.src"
                :alt="image.alt"
                :style="{ width: image.width }"
            >
        </div>
    </div>
</template>