<template>
  <b-media>
    <template #aside>
      <b-img id="logos" :src="image"></b-img>
      <div id="content">
        <h5 id="name" class="mt-0">{{ title }}</h5>
        <div id="urls">
          <b-button size="sm" variant="info" v-for="(item, index) in details" :id="`${title}-${index}`" :key="index"
            :href="item">
            Open {{ index >= 1 ? index + 1 : "" }}
            <b-tooltip class="text-center" :target="`${title}-${index}`" tabindex="0">
              <img v-if="templateExists(templates[index])" id="ally-template" :src="templates[index]" />
              <p v-else id="ally-template">Template lost</p>
            </b-tooltip>
          </b-button>
        </div>
      </div>
    </template>
  </b-media>
</template>

<script>


export default {
  name: "Ally-Media",
  props: {
    title: {
      type: String,
      require: true
    },
    details: {
      type: Array,
      require: false
    },
    image: {
      props: String,
      require: true
    },
    templates: {
      props: Array,
      require: false
    }
  },
  methods: {
    templateExists(template) {
      return template && template.length > 0;
    },
    templateNotExists(template) {
      return !this.templateExists(template)
    }
  }
}
</script>

<style scoped>
#display {
  display: flex;
  flex-direction: column;
}

#name {
  margin-bottom: 0;
}

#content {
  margin-left: 1em;
}

#logos {
  width: 3.5rem;
  height: auto;
  border-radius: 10px;
}

#urls {
  display: flex;
  gap: .5em;
}

#ally-template {
  width: 5em;
}
</style>