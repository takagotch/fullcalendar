### fullcalendar
---
https://github.com/fullcalendar/fullcalendar

```
<link rel='stylesheet' href="fullcalendar/fullcalendar.css" />
<script src='lib/jquery.min.js'></script>
<script src='lib/moment.min.js'></script>
<script src='fullcalendar/fullcalendar.js'></script>

<div id='calendar'></div>
```

```
npm install jquery fullcalendar
```

```js
import $ from 'jquery';
import 'fullcalendar';

$(function(){
  $('#calendar').fullCalendar({
   //
  })
});

$('#calendar').fullCalendar({
  weekends: false
});

$('#calendar').fullCalendar({
  dayClick: function(){
    alert('a day has been clicked!');
  }
});

var calendar = $('#calendar').fullCalendar('getCalendar');
calendar.on('dayClick', funciton(date, jsEvent, view){
  console.log('clicked on ', date.format());
});

$('#calendar').fullCalendar('next');

var calendar = $('#calendar').fullCalendar('getCalendar');
calendar.next();

$('#calendar').fullCalendar({
  header: { center: 'month, agendaWeek' },
  views: {
    month: {
      titleFormat: 'YYYY, MM, DD'
    }
  }
});

$('#calendar').fullCalendar({
  views: {
    basic: {
    },
    agenda: {
    },
    week: {
    },
    day: {
    }
  }
});

var locale = $('#calendar').fullCalendar('option', 'locale');

$('#calendar').fullCalendar('option', 'locale', 'fr');

$('#calendar').fullCalendar('option', {
  locale: 'fr',
  isRTL: true
});

$('#my-tabs').tabs({
  activate: function(event, ui){
    $('#calendar').fullCalendar('render');
  }
});

$('#my-prev-button').click(function(){
  $('#calendar').fullCalendar('prev');
});

```

