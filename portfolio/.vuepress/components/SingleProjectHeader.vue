<template>
  <div class="header">

    <div class="column">
      <Label class="label">Project</Label>
      <span class="value">{{ title }}</span>
    </div>

    <div class="column">
      <Label class="label">Year</Label>
      <span class="value">{{ year }}</span>
    </div>

    <div class="column">
      <Label class="label">Categories</Label>
      <span class="value categories" v-for="category in categories" v-text="category" />
    </div>

  </div>
</template>

<script>
  export default {
    props: {
      title: {
        type: String,
        required: true
      },
      year: {
        type: String,
        required: true
      },
      categories: {
        type: Array,
        required: true
      }
    }
  }
</script>

<style scoped>

  .header {
    display: flex;
    padding: 2rem 0;
  }

  .column {
    flex: 0 0 33.33%;
  }

  .label {
    margin-bottom: 0.5rem;
  }

  .value {
    font-weight: 500;
  }

  .categories:after {
    content: ', ';
  }

  .categories:last-of-type:after {
    content: '';
  }

</style>
