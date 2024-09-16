<template>
  <q-page :padding="false">
    <PageHeader :pageTitle="Title" :breadcrumb="Breadcrumb" />
    <div id="page-contents">
      <slot></slot>
    </div>
  </q-page>
</template>

<script>
// Components:

export default {
  name: 'components-common-page',

  components: {
  },

  props: {
    Title: String,
    Breadcrumb: Object,
  },

  created() {
    if (this.Title == null) throw 'Defina o título da página';
    if (this.Breadcrumb == null) throw 'Defina o breadcrumb da página';
  }

}
</script>