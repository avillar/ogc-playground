<template>
  <v-container>
    <v-row>
      <v-col>
        <h2 v-if="tabTitle">{{tabTitle}} - TBD</h2>
        <h2 v-else>TBD</h2>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  props: {
    tabTitle: {
      type: String,
      required: false,
    }
  },

  data: () => ({

  })
}
</script>