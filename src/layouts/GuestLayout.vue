<script setup>
import Package from '../../package.json'
</script>

<template>
  <q-layout>
    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer bordered :class="{'bg-dark':$q.dark.isActive}" class="q-pa-xs">
      <div class="flex justify-between">
        <span class="text-caption">&copy; Elias Lazcano</span>
        <span class="text-caption">v{{ Package.version }}</span>
      </div>
    </q-footer>

    <q-page-sticky position="top-right" :offset="[16,16]" class="z-fab">
      <q-btn
        color="primary"
        :icon="$q.dark.isActive ? 'wb_incandescent' : 'dark_mode'"
        @click="$q.dark.toggle()"
        push round
      >
        <q-tooltip anchor="center left" self="center right" :offset="[10, 10]">
          TEMA {{ $q.dark.isActive ? 'CLARO' : 'ESCURO' }}
        </q-tooltip>
      </q-btn>
    </q-page-sticky>
  </q-layout>
</template>
