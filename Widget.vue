<template>
  <q-card class="q-ma-sm">
    <q-toolbar class="full-width bg-grey-6 text-white">
      <q-avatar v-if="!!Icon">
        <q-icon :name="Icon"></q-icon>
      </q-avatar>

      <q-toolbar-title>{{ Title }}</q-toolbar-title>

    </q-toolbar>
    <q-card-section>
      <div style="max-height:400px;">
        <slot></slot>
      </div>
    </q-card-section>
  </q-card>
</template>

<script>
export default {
  name: 'components-common-widget',

  props: {
    Icon: String,
    Title: String
  }
}
</script>