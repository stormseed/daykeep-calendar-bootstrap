<template>
  <div class="container">
    <div>
      <b-form-group>
        <b-form-checkbox-group
          v-model="showCards"
          :options="showCardOptions"
        ></b-form-checkbox-group>
      </b-form-group>
    </div>

    <b-card
      title="Full calendar component"
      v-if="showCards.includes('fullCalendar')"
    >
      <b-card-text>
        A multifunction component that displays calendar information in a variety of predefined formats.
      </b-card-text>
      <daykeep-calendar
        :event-array="eventArray"
        :sunday-first-day-of-week="false"
        NOcalendar-locale="fr"
        NOcalendar-timezone="America/Los_Angeles"
        NOevent-ref="MYCALENDAR"
        :allow-editing="true"
        agenda-style="block"
        :render-html="true"
        :NOstart-date="new Date(2019, 1, 4)"
      />
    </b-card>


    <b-card
      title="Individual month view component"
      v-if="showCards.includes('month')"
    >
      <b-card-text>
        Example of a single component displayed. Acts independently of any other calendar component on the same page.
      </b-card-text>
      <daykeep-calendar-month
        :event-array="eventArray"
        :sunday-first-day-of-week="false"
        calendar-locale="fr"
      />
    </b-card>


    <b-card
      title="Individual multi-day / week view component"
      v-if="showCards.includes('week')"
    >
      <b-card-text>
        The multi-day component. This can be configured as a proper full-week display (shown), a single day or a multi-day. The number of days shown and the number of days moved in the navigation are adjustable.
      </b-card-text>
      <daykeep-calendar-multi-day
        :event-array="eventArray"
        scrollHeight="400px"
        day-cell-height="7"
        day-cell-height-unit="rem"
        :show-half-hours="true"
      />
    </b-card>

  </div>
</template>

<script>
  import {
    BCard,
    BCardText,
    BFormGroup,
    BFormCheckboxGroup
  } from 'bootstrap-vue/es/components'
  import {
    DaykeepCalendar,
    DaykeepCalendarMonth,
    DaykeepCalendarMultiDay
    // DaykeepCalendarAgenda
  } from './'
  import {
    MoveDates,
    sampleEventArray
  } from 'daykeep-calendar-core/demo'
  export default {
    name: 'PageIndex',
    components: {
      BCard,
      BCardText,
      BFormGroup,
      BFormCheckboxGroup,
      DaykeepCalendar,
      DaykeepCalendarMonth,
      DaykeepCalendarMultiDay
      // DaykeepCalendarAgenda
    },
    mixins: [ MoveDates ],
    data () {
      return {
        eventArray: sampleEventArray, // in page-code-mixins/sample-data.js
        showCards: ['fullCalendar'],
        showCardOptions: [
          { text: 'Full calendar', value: 'fullCalendar' },
          { text: 'Month', value: 'month' },
          { text: 'Week', value: 'week' },
          { text: 'Agenda', value: 'agenda' }
        ]
      }
    },
    computed: {},
    methods: {},
    created () {
      this.moveSampleDatesAhead()
    }
  }
</script>

<style lang="stylus">
</style>
