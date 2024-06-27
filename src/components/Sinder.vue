<template>
  <div id="content" class="container">
    <h2>Templates</h2>
    <div id="card-container">
      <Card v-for="item in templates" :key="item.id" :title="item.title" :description="item.description"
        :image="item.image" :href="item.href" :alternatives="item.alternatives" :vertical="verticalCards"></Card>
    </div>
    <hr>
    <h2>Notifications</h2>
    <div>
      <b-table :fields="fields" :items="audioFiles">
        <template #cell(playback)="data">
          <span>
            <audio controls>
              <source :src="data.value" type="audio/mpeg">
              Your browser does not support the audio element.
            </audio>
          </span>
        </template>
      </b-table>


    </div>
  </div>
</template>

<script>
import Template from './Cards.vue'

import mainTemplate from '@/assets/sinder/main.png'
import tofTemplate from '@/assets/sinder/tof.png'
import makeupTemplate from '@/assets/sinder/makeup.png'

export default {
  name: "Sinder-canvas",
  components: {
    Card: Template
  },
  data() {
    return {
      templates: [
        {
          id: 0,
          title: "Main Template",
          description: "Main template used by The Swarm.\nImage might be outdated but the button goes to the newest version.",
          image: mainTemplate,
          href: "https://osutemplate.osupxlshosting.ovh/sinder/",
          alternatives: [{ label: "Dots", href: "https://osutemplate.osupxlshosting.ovh/sinder-dot" }]
        },
        {
          id: 1,
          title: "Tof",
          description: "Tof template from Anny's community.",
          image: tofTemplate,
          href: "https://sinder.pxls.world/#x=861&y=732&scale=35.04&template=https%3A%2F%2Fi.imgur.com%2FO2rVQyC.png&ox=845&oy=720&tw=-1&title=toffee&convert=nearestCustom"
        },
        {id: 2,
          title: "Neuro's Makeup",
          description: "Biggest project The Swarm is taking on.",
          image: makeupTemplate,
          href: "https://sinder.pxls.world/#x=109&y=1204&scale=10.66&template=https%3A%2F%2Fi.imgur.com%2FQHLKmdJ.png&ox=0&oy=1132&tw=184&title=Makeup&convert=nearestCustom"
        }
      ],
      fields: ["name", "url", "playback"],
      audioFiles: [
        { name: "Neuro Meow", url: "https://evilneuro.com/audio/neuro-meow.mp3", playback: '/audio/neuro-meow.mp3' },
        { name: "Neuro Bwaa", url: "https://evilneuro.com/audio/neuro-bwaa.mp3", playback: '/audio/neuro-bwaa.mp3' },
        { name: "Neuro Got Ammunition", url: "https://evilneuro.com/audio/neuro-gotammunition", playback: '/audio/neuro-gotammunition.mp3' },
        { name: "Neuro Pizza Time", url: "https://evilneuro.com/audio/neuro-pizzatime.mp3", playback: '/audio/neuro-pizzatime.mp3' },
        { name: "Evil KEK", url: "https://evilneuro.com/audio/evil-kek.mp3", playback: '/audio/evil-kek.mp3' },
        { name: "Evil Dink Donk", url: "https://evilneuro.com/audio/evil-dinkdonk.mp3", playback: '/audio/evil-dinkdonk.mp3' },
        { name: "Evil AAAAAAH", url: "https://evilneuro.com/audio/evil-AAAAH.mp3", playback: '/audio/evil-AAAAH.mp3' },
        { name: "Evil Fuck", url: "https://evilneuro.com/audio/evil-fuck.mp3", playback: '/audio/evil-fuck.mp3'},
      ]
    }
  },
  computed: {
    verticalCards() {
      return this.templates.length > 2
    }
  }
};
</script>

<style scoped>
#content {
  border-width: 1px;
}

#card-container {
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
}
</style>
