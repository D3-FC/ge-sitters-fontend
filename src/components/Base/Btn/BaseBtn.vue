<template>
  <QBtn
    :color="color"
    :label="label"
    :type="type"
    no-caps
    rounded
    unelevated
  >
    <slot/>
  </QBtn>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component({})
export default class BaseBtn extends Vue {
  $refs: any
  @Prop(String) label?: string
  @Prop({
    type: String,
    default: 'primary'
  }) color?: string

  @Prop(String) type?: string

}
</script>

<style
  lang="scss"
  module
>
.main {

}
</style>
