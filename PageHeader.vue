<template>
  <div class="row">
    <div class="col-sm-12 col-md-6">
      <h4 class="gt-xs">{{ pageTitle }}</h4>
      <div class="lt-sm text-h5 q-mt-md">{{ pageTitle }}</div>
    </div>
    <div class="col-sm-12 col-md-6">
      <q-breadcrumbs class="q-py-lg q-px-md float-right">
        <q-breadcrumbs-el v-for="(item, index) in breadcrumb" :key="index" :label="item.label" :icon="item.icon"
          :to="item.to" />
      </q-breadcrumbs>
    </div>
  </div>
</template>

<script>
export default {
  name: 'page-header-component',

  props: {
    pageTitle: String,
    breadcrumb: Array
  }
}
</script>
