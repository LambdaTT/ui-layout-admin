<template>
  <q-dialog :full-width="FullWidth" @hide="hideFn" @show="showFn" :persistent="Persistent" v-model="show">
    <q-card>
      <q-toolbar class="full-width bg-teal text-white">
        <q-avatar v-if="!!Icon">
          <q-icon :name="Icon"></q-icon>
        </q-avatar>

        <q-toolbar-title v-if="!!Title">{{ Title }}</q-toolbar-title>

        <q-btn flat round dense icon="close" v-close-popup />
      </q-toolbar>

      <q-card-section class="q-pa-none q-pa-md-md">
        <slot></slot>
      </q-card-section>

      <q-card-actions class="justify-end">
        <q-btn dense label="Fechar" color="grey-8" icon="close" v-close-popup></q-btn>
        <div v-if="!HideActions">
          <q-btn dense class="q-ml-sm" v-show="!action.hide" v-for="action in Actions" :key="action.label" :label="action.label"
            :color="action.color" :icon="action.icon" @click="action.fn"></q-btn>
        </div>
      </q-card-actions>
    </q-card>
  </q-dialog>
</template>
<script>
export default {
  name: 'ui-layoutadmin-modal',

  props: {
    Title: String,
    Icon: String,
    Persistent: Boolean,
    Actions: Array,
    Data: Object,
    HideActions: Boolean,
    modelValue: Boolean,
    FullWidth: Boolean
  },

  data() {
    return {
      show: false
    }
  },

  watch: {
    show(val) {
      this.$emit('update:model-value', val);
    },

    modelValue(val) {
      this.show = val;
    }
  },

  methods: {
    hideFn() {
      setTimeout(() => this.$emit('hide'), 100);
    },

    showFn() {
      setTimeout(() => this.$emit('show'), 100);
    }
  },
}
</script>