<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="flex justify-between items-center q-pa-md">
      <q-icon name="keyboard_arrow_left" size="25px"> </q-icon>
      <q-toolbar-title class="text-center"> Master Learning </q-toolbar-title>
      <q-btn
        flat
        dense
        round
        icon="menu"
        aria-label="Menu"
        @click="leftDrawerOpen = !leftDrawerOpen"
      />
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label header class="text-grey-8">
          Master Learning First Project
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from "components/EssentialLink.vue";

const linksData = [
  {
    title: "Inicio",
    caption: "Inicio da Aplicação",
    icon: "school",
    link: "https://quasar.dev",
  },
  {
    title: "Cursos",
    caption: "ir para site de Cursos",
    icon: "code",
    link: "https://jacode.com.br",
  },
];

export default {
  name: "MainLayout",
  components: {
    EssentialLink,
  },
  data() {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData,
    };
  },
};
</script>

<style lang="stylus">
.q-header {
  background-color: #f95179;
}
</style>
