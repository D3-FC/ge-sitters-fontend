<template>
  <QInput
    outlined
    v-model="valueProxy"
    dense
    :error="hasError"
    no-error-icon
    hide-bottom-space
    :placeholder="placeholder"
    :tabindex="tabindex"
    ref="input"
    :type="type"
  />
</template>

<script lang="ts">
import { Component, Prop } from 'vue-property-decorator'
import { mixins } from 'vue-class-component'
import { CanBeInsideField } from '../Field/CanBeInsideField'
import { AutofocusInputMixin } from './AutofocusInputMixin'

@Component
export default class BaseInputText extends mixins(CanBeInsideField, AutofocusInputMixin) {
  $refs: any

  @Prop({
    type: String,
    required: true
  }) value!: String

  @Prop(String) placeholder?: string
  @Prop(String) tabindex?: string
  @Prop(String) type?: string

  @Prop(String) error?: string

  get valueProxy () {
    return this.value
  }

  set valueProxy (v: any) {
    this.$emit('input', v)
  }

}
</script>

<style
  lang="scss"
  module
>
.main {

}
</style>
