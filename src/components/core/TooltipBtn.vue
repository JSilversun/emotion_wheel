<template>
  <span class="v-app-tooltip-btn d-inline-block">
    <v-tooltip
      bottom
      content-class="v-app-tooltip-btn__content"
      open-delay="200"
    >
      <template #activator="{ on }">
        <v-btn
          :aria-label="path"
          icon
          v-bind="$attrs"
          v-on="{
            ...on,
            ...$listeners
          }"
        >
          <slot v-if="$slots.icon" name="icon" />

          <v-icon v-else v-text="icon" />
        </v-btn>
      </template>
      <span class="d-inline-block capitalize-fl">{{ $t(path) }}</span>
    </v-tooltip>
  </span>
</template>

<script>
export default {
  name: "TooltipBtn",
  props: {
    icon: String,
    path: String
  }
};
</script>

<style lang="sass">
.v-app-tooltip-btn__content p
    margin: 0
</style>
