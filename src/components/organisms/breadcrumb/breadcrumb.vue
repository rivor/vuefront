<template>
  <vf-m-container :class="{'mb-3': breadcrumbs.length > 0}" class="vf-o-breadcrumb">
    <vf-m-breadcrumb v-if="loaded && breadcrumbs.length > 0">
      <vf-m-breadcrumb-item>{{$t('elements.common.home.titleText')}}</vf-m-breadcrumb-item>
      <vf-m-breadcrumb-item
        v-for="(value, key) in breadcrumbs"
        :key="key"
        :to="value.to"
      >{{ value.title }}</vf-m-breadcrumb-item>
    </vf-m-breadcrumb>
    <vf-l-o-breadcrumb v-else-if="!loaded" />
  </vf-m-container>
</template>
<script>
import { mapGetters } from "vuex";

export default {
  computed: {
    ...mapGetters({
      breadcrumbs: "common/breadcrumbs/get",
      loaded: "common/breadcrumbs/loaded"
    })
  }
};
</script>