<template>
  <div :class="{ 'component': true, 'component--open': showDetails } ">
    <div class="component__content">
        <label class="component__label">
          <h3 class="component__name"> {{ name }} </h3>
          <slot/>
        </label>
        <span class="component__code"> Code: {{ code }} </span>
        <button type="button" class="component__detail-btn" @click.prevent="toggleDetails()"> {{showDetails === false? 'Show Details' : 'Hide Details'}} </button>
        <p v-if="showDetails" class="component__details"> {{ details }} </p>
    </div>
  </div>
</template>

<script>

export default {
  name: 'TreetopComponent',
  props: {
    name: String,
    code: Number,
    details: String,
  },
  data() {
    return {
      showDetails: false,
      selectedComponents: [
      ],
    }
  },
  mounted() {
  },
  methods: {
    toggleDetails() {
      return this.showDetails = !this.showDetails;
    },

  },
}
</script>
<style scoped lang="scss">

h3 {
  margin: 40px 0 0;
}

.component {
  display: flex;
  justify-content: flex-start;
  align-items: flex-start;
  width: 20rem;
  height: 7rem;
  margin-bottom: 1rem;
  text-align: left;
  &--open {
    height: unset;
  }

  &__content {
    display: flex;
    flex-direction: column;
  }

  &__label {
    display: flex;
    align-items: baseline;
  }

  &__code {
    margin-top: 0.5rem;
  }

  &__detail-btn {
    margin-top: 0.5rem;
    width: 6rem;
  }

  &__details {
  }
}
</style>
