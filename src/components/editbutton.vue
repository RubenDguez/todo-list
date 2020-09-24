<template>
  <v-speed-dial
    v-model="fab"
    :right="right"
    :left="left"
    :direction="direction"
    :open-on-hover="hover"
    :transition="transition"
  >
    <template v-slot:activator>
      <v-btn
        v-model="fab"
        fab
        elevation="0"
        color="transparent"
        hover="none"
        x-small
      >
        <v-icon v-if="fab">mdi-close</v-icon>
        <v-icon v-else>mdi-dots-horizontal </v-icon>
      </v-btn>
    </template>

    <v-btn fab dark x-small color="green">
      <v-icon>mdi-check</v-icon>
    </v-btn>

    <v-btn fab dark x-small color="orange">
      <v-icon>mdi-pencil</v-icon>
    </v-btn>
    <v-btn fab dark x-small color="red">
      <v-icon>mdi-delete</v-icon>
    </v-btn>
  </v-speed-dial>
</template>


<script>
export default {
  name: "EditButton",

  data: () => ({
    direction: "left",
    fab: false,
    fling: false,
    hover: false,
    tabs: null,
    top: false,
    right: true,
    bottom: true,
    left: false,
    transition: "slide-y-reverse-transition",
  }),
};
</script>