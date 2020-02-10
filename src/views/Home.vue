<template>
  <div class="home">
    <section class="home">
      <img alt="Clevy logo" src="../assets/ca_logo.svg" />
    </section>

    <section id="intents" class="intents">
      <!-- The new intents will come here -->
      <div
        id="addIntent"
        class="intent"
        role="button"
        @click="showModal = true"
      >
        <p>New intent</p>
      </div>
      <modal v-if="showModal" @close="showModal = false">
        <h3 slot="header">custom header</h3>
      </modal>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
import Modal from "../components/Modal";
export default {
  name: "home",
  components: {
    Modal
  },
  data: function() {
    return {
      showModal: false
    };
  }
};
</script>

<style lang="scss">
$main-color: #e9dccd;
$secondary-color: #df8e24;
$content-color: #555353;
$border-radius: 5px;

@mixin intent {
  margin: 0.5rem;
  font-size: 0.8rem;
  width: 12rem;
  min-height: 6rem;
  background: white;
  color: $content-color;
  border-radius: $border-radius;
}

.home {
  margin: 2.5rem auto;
  text-align: center;
}

// Intents
.intents {
  margin: 0 2rem;
  display: flex;
  flex-direction: row;
  justify-content: center;
  flex-wrap: wrap;
}

.intent {
  @include intent;
  text-align: center;
  font-weight: bold;
  padding: 2.5rem 0;
  border: 1px dashed $secondary-color;
  cursor: pointer;
  opacity: 0.6;
}
</style>
