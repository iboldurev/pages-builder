<template lang="pug">
  #artboard.artboard
    component(v-for='section in $builder.sections'
      :is='section.name'
      :key='section.id'
      :id='section.id')
</template>

<script>
export default {
  name: 'builder-render',

  props: {
    data: {
      type: Object,
      default: () => ({
        title: '',
        sections: []
      })
    }
  },

  created () {
    this.$builder.set(this.data)
    this.$builder.isEditing = false
  }
}
</script>
