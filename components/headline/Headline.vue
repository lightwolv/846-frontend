<template>
  <div :class="`${rootClassName}`">
    <h2 :class="`${rootClassName}--h2`">
      {{ content }}
    </h2>
    <div v-if="date !== ''" :class="`${rootClassName}--p`">
      {{ date }}
    </div>
  </div>
</template>

<script>
import { ClassNames as GlobalClassNames } from '~/shared/constants'

export default {
  props: {
    content: {
      type: String,
      default() {
        return 'Headline'
      }
    },
    date: {
      type: String,
      default() {
        return ''
      }
    }
  },
  data() {
    return {
      rootClassName: `${GlobalClassNames.PREFIX}-cHeadline`
    }
  }
}
</script>

<style lang="scss">
.#{$CLASSNAME_PREFIX}-cHeadline {
  &--h2 {
    font-size: 38px;
    font-weight: 800;
    line-height: 1.2;
    padding-left: 10px;
    color: white;
  }
  &--p {
    margin-top: 0.5em;
    margin-bottom: 2em;
    padding-left: 10px;
    font-size: 16px;
    font-weight: 400;
    line-height: 1.2;
    color: #bbbbbb;
  }
}
</style>
