<template>
  <div>TEST</div>
</template>

<script>
  // import {
  //   QList,
  //   QItem,
  //   QItemSection,
  //   QAvatar,
  //   QChip,
  //   QIcon,
  //   QBadge,
  //   QDialog,
  //   CloseDialog,
  //   QCard,
  //   QCardSection,
  //   QToolbar,
  //   QToolbarTitle,
  //   QBtn,
  //   QCheckbox,
  //   QInput,
  //   QEditor
  // } from 'quasar'
  import {
    CalendarMixin,
    EventPropsMixin,
    CalendarEventDetailTemplateMixin
  } from 'daykeep-calendar-core'
  // import {
  //   QuasarFieldDate as FieldDate,
  //   QuasarFieldTime as FieldTime
  // } from '../../fields'

  export default {
    name: 'CalendarEventDetail',
    mixins: [
      CalendarMixin,
      EventPropsMixin,
      CalendarEventDetailTemplateMixin
    ]
    // components: {
    //   QList,
    //   QItem,
    //   QItemSection,
    //   QAvatar,
    //   QChip,
    //   QIcon,
    //   QBadge,
    //   QDialog,
    //   QCard,
    //   QCardSection,
    //   QToolbar,
    //   QToolbarTitle,
    //   QBtn,
    //   QCheckbox,
    //   QInput,
    //   QEditor,
    //   FieldDate,
    //   FieldTime
    // },
    // directives: {
    //   CloseDialog
    // }
  }
</script>

<style lang="stylus">
  //@import '~daykeep-calendar-core/component/calendar/styles-common/calendar.vars.styl'

  $topSidePadding = 16px
  $listSideItemWidth = 38px
  $listSideItemSpace = 10px
  $forcedLeftMargin = $topSidePadding + $listSideItemWidth + $listSideItemSpace

  .calendar-event-detail
    max-width 80vw !important
    .ced-icon-div-with-badge
      padding-right 5px
      padding-top 5px
    .ced-close-button-left-spacer
      width 16px
    .ced-event-title
      font-size 1.5em
      font-weight 500
    .ced-list-title
      font-size 1em
    .ced-list-subtitle
      font-size .8em
      opacity 0.8
    .ced-q-card-main
      padding-top 0
    .ced-avatar-column
      min-width 40px
      margin-right 16px
    .ced-top
      /*padding .25em 0 1em*/
      .ced-top-title
        font-size 1.25em
        margin-left $forcedLeftMargin
        .ced-toolbar-edit-spacer
          min-height 1em
          height 1em
      .ced-edit-button-container
        position relative
        .ced-edit-button
          position absolute
          left 8px
          bottom -32px
    .ced-content
      font-size 1em
      .ced-edit-button-content-spacer
        min-height 1em
        height 1em
    .ced-nested-item
      padding-left 0
    .ced-small-inverted-icon
      font-size 20px
      padding 2px
      border-radius 50%
      min-width 24px
      .q-item-icon-inverted
        // background lighten($light, 25%)
</style>
