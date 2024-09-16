<template>
  <q-card>
    <q-card-section class="q-pa-lg bg-teal text-white">
      <!--Card Header-->
      <div class="row">
        <div class="col-12 col-md-6">
          <span class="text-h6">
            <q-icon v-if="!!Icon" :name="Icon" size="md"></q-icon>
            <span v-if="!!Icon">&nbsp;</span>
            {{ Title }}
          </span>
        </div>
        <div class="col-12 col-md-6 text-right">
          <slot name="actions"></slot>
        </div>
      </div>
    </q-card-section>

    <!--Main Section-->
    <q-card-section>
      <slot></slot>
    </q-card-section>

    <!--Secondary Sections-->
    <div v-for="(section, name) in $slots" :key="name">
      <q-separator v-if="name != 'actions' && name != 'default'"></q-separator>
      <q-card-section v-if="name != 'actions' && name != 'default'">
        <slot :name="name"></slot>
      </q-card-section>
    </div>
  </q-card>
</template>

<script>
export default {
  name: 'components-common-card',

  props: {
    Title: String,
    Icon: String
  }
}
</script>