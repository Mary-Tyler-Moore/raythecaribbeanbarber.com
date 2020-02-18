<template>
  <q-layout view="hHh lpR fFf">
    <q-header bordered class="bg-blue-grey-10 text-white" height-hint="98">
      <q-toolbar>
        <q-toolbar-title>
          <q-btn
            v-if="$q.platform.is.mobile"
            label="Ray 😎"
            flat
            size="xl"
            :ripple="{ center: true }"
            @click="scrollTo('top')"
          />
          <q-btn
            v-if="$q.platform.is.desktop"
            label="Ray 🏝️ The Caribbean Barber 💈"
            flat
            size="xl"
            :ripple="{ center: true }"
            @click="scrollTo('top')"
          />
        </q-toolbar-title>

        <q-tabs style="margin-right: 2.5em">
          <q-tab
            @click="scrollTo('portfolio')"
            label="Portfolio"
            :ripple="{ center: true }"
          />
          <q-tab
            @click="scrollTo('resume')"
            label="Resume"
            :ripple="{ center: true }"
          />
          <q-tab
            @click="scrollTo('about')"
            label="About"
            :ripple="{ center: true }"
          />
          <q-tab
            @click="scrollTo('contact')"
            label="Contact"
            :ripple="{ center: true }"
          />
        </q-tabs>
        <!-- Dark Mode Toggle -->
        <q-btn
          :icon="$q.dark.isActive ? 'brightness_3' : 'wb_sunny'"
          flat
          class="absolute-right"
          style="margin-right: .6em"
          dense
          round
          @click="$q.dark.isActive ? $q.dark.set(false) : $q.dark.set(true)"
        ></q-btn>
        <!-- Dark Mode Toggle -->
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: "MainLayout",

  components: {},

  data() {
    return {};
  },

  methods: {
    scrollTo(id) {
      document
        .getElementById(id)
        .scrollIntoView({ block: "end", behavior: "smooth" });
    }
  }
};
</script>
