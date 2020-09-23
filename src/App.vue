<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app clipped>
      <v-list dense>
        <v-subheader class="mt-4 grey--text text--darken-1">TODAY</v-subheader>

        <v-list-item v-for="item in items" :key="item.text" link>
          <v-list-item-action>
            <v-icon>mdi-format-list-checks</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>
              {{ item.title }}
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-subheader class="mt-4 grey--text text--darken-1"
          >SUBSCRIPTIONS</v-subheader
        >
        <v-list>
          <v-list-item v-for="item in items2" :key="item.text" link>
            <v-list-item-avatar>
              <img
                :src="`https://randomuser.me/api/portraits/men/${item.picture}.jpg`"
                alt=""
              />
            </v-list-item-avatar>
            <v-list-item-title v-text="item.text"></v-list-item-title>
          </v-list-item>
        </v-list>
        <v-list-item class="mt-4" link>
          <v-list-item-action>
            <v-icon color="grey darken-1">mdi-plus-circle-outline</v-icon>
          </v-list-item-action>
          <v-list-item-title class="grey--text text--darken-1"
            >Browse Channels</v-list-item-title
          >
        </v-list-item>
        <v-list-item link>
          <v-list-item-action>
            <v-icon color="grey darken-1">mdi-cog</v-icon>
          </v-list-item-action>
          <v-list-item-title class="grey--text text--darken-1"
            >Manage Subscriptions</v-list-item-title
          >
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app clipped-left color="red" dense>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-icon class="mx-4" large> mdi-clipboard-outline </v-icon>
      <v-toolbar-title class="mr-12 align-center">
        <span class="title">TODO LIST</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-row align="center" style="max-width: 650px">
        <v-text-field
          :append-icon-cb="() => {}"
          placeholder="Search..."
          single-line
          append-icon="mdi-magnify"
          color="white"
          hide-details
        ></v-text-field>
      </v-row>
    </v-app-bar>

    <v-main>
      <v-container class="fill-height">
        <v-row justify="center" align="center">
          <v-col class="shrink"> </v-col>
          <EditButton />
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import EditButton from "@/components/editbutton.vue";

export default {
  props: {
    source: String,
  },
  components: {
    EditButton,
  },
  data: () => ({
    drawer: null,
    items: [
      {
        id: 1,
        title: "first todo",
        description: "pick up milk",
        complete: true,
        canceled: true,
        date: 1389878466730,
      },
      {
        id: 2,
        title: "second todo",
        description: "learn backbone",
        complete: false,
        canceled: false,
        date: 1389988926901,
      },
      {
        id: 3,
        title: "third todo",
        description: "go for a run",
        complete: false,
        canceled: false,
        date: 1389992494240,
      },
      {
        id: 4,
        title: "fourth todo",
        description: "go for a run",
        complete: false,
        canceled: false,
        date: 1389992494250,
      },
    ],
    items2: [
      { picture: 28, text: "Joseph" },
      { picture: 38, text: "Apple" },
      { picture: 48, text: "Xbox Ahoy" },
      { picture: 58, text: "Nokia" },
      { picture: 78, text: "MKBHD" },
    ],
  }),
  created() {
    this.$vuetify.theme.dark = true;
  },
};
</script>

