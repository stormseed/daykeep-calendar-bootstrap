<template>
  <div class="calendar-header flex-col-auto flex-row flex-justify-between flex-items-center">
    <div class="calendar-header-left flex-col-auto">
      <b-button
        @click="doMoveTimePeriod(timePeriodUnit, -timePeriodAmount)"
      >
        Prev
      </b-button>
    </div>
    <div class="calendar-header-label">
      <slot/>
    </div>
    <div class="calendar-header-right flex-col-auto">
      <b-button
        @click="doMoveTimePeriod(timePeriodUnit, timePeriodAmount)"
      >
        Next
      </b-button>
    </div>
  </div>
</template>

<script>
  import { CalendarHeaderNavTemplateMixin } from 'daykeep-calendar-core'
  import { BButton } from 'bootstrap-vue/es/components'

  export default {
    name: 'CalendarHeaderNav',
    mixins: [ CalendarHeaderNavTemplateMixin ],
    components: {
      BButton
    }
  }
</script>

<style lang="stylus">
  .calendar-header
    .calendar-month-year
      font-size 1.25em
      font-weight bold
</style>
