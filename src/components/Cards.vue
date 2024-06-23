<template>
  <div id="container">
    <div v-if="vertical">
      <b-card :title="title" :img-src="image" style="max-width: 20em;">
        <b-card-text>
          {{ description }}
        </b-card-text>

        <div id="buttons">
          <b-button :href="href" variant="primary">Open</b-button>
          <b-button v-for="(alt, index) in alternatives" :key="index" :href="alt.href" variant="secondary">{{
            alt.label }}</b-button>
        </div>
      </b-card>
    </div>
    <div v-if="!vertical">
      <b-card no-body class="overflow-hidden h-100" style="max-width: 540px">
        <b-row no-gutters>
          <b-col md="6">
            <b-card-img :src="image" class="rounded-0"
              style="height: 15em; width: auto; image-rendering: crisp-edges; image-rendering: pixelated;"></b-card-img>
          </b-col>
          <b-col md="6">
            <b-card-body :title="title">
              <b-card-text>
                {{ description }}
              </b-card-text>
              <div id="buttons">
                <b-button :href="href" variant="primary">Open</b-button>
                <b-button v-for="(alt, index) in alternatives" :key="index" :href="alt.href" variant="secondary">{{
                  alt.label }}</b-button>
              </div>
            </b-card-body>
          </b-col>
        </b-row>
      </b-card>
    </div>
  </div>
</template>

<script>
export default {
  name: "Template-card",
  props: {
    vertical: {
      type: Boolean,
      required: false
    },
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    image: {
      type: String,
      required: true
    },
    href: {
      type: String,
      required: true
    },
    alternatives: {
      type: Array,
      required: false,
      default: () => []
    }
  },
}
</script>

<style scoped>
#container {
  margin-bottom: 1em;
}

#buttons {
  display: flex;
  justify-content: space-between;
}
</style>