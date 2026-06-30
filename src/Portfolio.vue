<script setup>
const imageUrl = (path) => new URL(`../media/portfolio/${path}`, import.meta.url).href

const projects = [
  {
    title: "Self Driving Challenge",
    description: "Vanuit het RDW is er een challenge opgezet om een zelfrijdende kart te maken. Ik en mijn team hebben meegedaan aan de closed categorie, wat betekend dat we een gebouwde kart krijgen en dat we alleen de software hoeven te bouwen.",
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
    description: "Tidalis is geinteresseerd geweest in het localiseren van schepen in de haven met camera's omdat radar niet altijd even accuraat is. Ik en mijn team hebben een proof of concept gemaakt om te laten zien dat het mogelijk is om schepen te localiseren met camera's.",
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
    description: "Vanuit de opleiding kregen wij een project waarbij wij een pinautomaat moesten maken. Ik en mijn team hebben een pinautomaat gemaakt die ook connectie kan maken met een centrale server zodat je ook bij andere pinautomaten kan pinnen.",
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
    description: "Als keuzevak hebben wij een project gekregen waarbij wij stoplichten moesten maken. Dit zou dan gebruikt worden om kinderen op de basisschool te leren oversteken.",
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
    description: "Vanuit de opleiding kregen wij een project waarbij wij een container mover moesten maken. Dit autotje moest dan over een parkours rijden en stoppen bij het einde.",
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
    description: "Vanuit de opleiding kregen wij een project waarbij wij een lift moesten maken. Ik en mijn team hebben een lift gemaakt die werkt met een motor en een sensorkoppeling.",
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