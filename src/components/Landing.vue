<template>
  <div>
    <div id="banner">
      <div id="layer">
        <div id="card">
          <h1>Neurocord's Pixel Resources</h1>
          <div id="hotlinks" class="h3">
            <a href="https://discord.gg/neurosama"><b-icon icon="discord"></b-icon></a>
            <a href="https://twitch.tv/vedal987"><b-icon icon="twitch"></b-icon></a>
            <a href="https://twitter.com/NeurosamaAI"><b-icon icon="twitter"></b-icon></a>
            <a href="https://youtube.com/@Neurosama"><b-icon icon="youtube"></b-icon></a>
          </div>
        </div>
      </div>
    </div>
    <b-container id="content">
      <div>
        <b-tabs pills>
          <b-tab title="Sinder" active>
            <hr />
            <Sinder />
          </b-tab>
          <b-tab title="Subathon" disabled>
            <hr />
          </b-tab>
          <b-tab title="r/Place 2023" disabled>
            <hr />
          </b-tab>
          <b-tab title="CdawgVA">
            <hr />
            <Connor />
          </b-tab>
        </b-tabs>
      </div>
    </b-container>
  </div>
</template>

<script>
import Sinder from "./Sinder.vue";
import Connor from "./Connor.vue";

export default {
  name: "Landing-Page",
  components: {
    Sinder: Sinder,
    Connor: Connor,
  },
};
</script>

<style scoped>

#banner {
  width: 100vw;
  height: 25em;
  background-image: url("@/assets/hug.jpg");
  background-size: cover;
  background-position-y: 75%;
}

#layer {
  width: inherit;
  height: inherit;
  background: rgb(2, 0, 36, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

#card {
  background-color: rgba(0, 0, 0, 0.5);
  padding: 1em;
  border-radius: 20px;
  color: white;
}

#hotlinks {
  display: flex;
  justify-content: space-evenly;
}

#hotlinks>a {
  transition: all 0.25s ease;
}

#hotlinks>a,
a:visited {
  color: white;
}

#hotlinks>a:hover {
  color: pink;
}

#content {
  margin-top: 1em;
  background-color: white;
}
</style>
