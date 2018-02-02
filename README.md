![downloads](https://img.shields.io/npm/dt/react-datetime-picker.svg) ![build](https://img.shields.io/travis/wojtekmaj/react-datetime-picker.svg) ![dependencies](https://img.shields.io/david/wojtekmaj/react-datetime-picker.svg
) ![dev dependencies](https://img.shields.io/david/dev/wojtekmaj/react-datetime-picker.svg
) [![tested with jest](https://img.shields.io/badge/tested_with-jest-99424f.svg)](https://github.com/facebook/jest)

# React-DateTime-Picker
An input component for picking date and time for your React application.

## tl;dr
* Install by executing `npm install react-datetime-picker` or `yarn add react-datetime-picker`.
* Import by adding `import DateTimePicker from 'react-datetime-picker'`.
* Use by adding `<DateTimePicker />`. Use `onChange` prop for getting new values.

## Demo

Minimal demo page is included in sample directory.

[Online demo](http://projekty.wojtekmaj.pl/react-datetime-picker/) is also available!

## Looking for *just* a date picker or a time picker?

React-DateTime-Picker will play nicely with [React-Date-Picker](https://github.com/wojtekmaj/react-date-picker) and [React-Time-Picker](https://github.com/wojtekmaj/react-time-picker). Check them out!

## Getting started

### Compatibility

[React-Calendar](https://github.com/wojtekmaj/react-calendar), on which React-DateTime-Picker relies heavily, uses modern web technologies. That's why it's so fast, lightweight and easy to style. This, however, comes at a cost of supporting only modern browsers.

|Browser|Minimum supported version|
|----|----|
|Google Chrome|24|
|Mozilla Firefox|29|
|Microsoft Edge|12|
|Apple Safari|10|
|Apple Safari (iOS)|10.2|
|Opera|15|
|Internet Explorer|11|
|Samsung Internet|4|

#### Legacy browsers

If you need to support legacy browsers like Internet Explorer 10, you will need to use [Intl.js](https://github.com/andyearnshaw/Intl.js/) or another Intl polyfill along with React-DateTime-Picker.

### Installation

Add React-DateTime-Picker to your project by executing `npm install react-datetime-picker` or `yarn add react-datetime-picker`.

### Usage

Here's an example of basic usage:

```js
import React, { Component } from 'react';
import DateTimePicker from 'react-datetime-picker';

class MyApp extends Component {
  state = {
    date: new Date(),
  }

  onChange = date => this.setState({ date })

  render() {
    return (
      <div>
        <DateTimePicker
          onChange={this.onChange}
          value={this.state.date}
        />
      </div>
    );
  }
}
```

### Custom styling

If you don't want to use default React-DateTime-Picker styling to build upon it, you can import React-DateTime-Picker by using `import DateTimePicker from 'react-datetime-picker/dist/entry.nostyle';` instead.

## User guide

### DateTimePicker

Displays an input field complete with custom inputs, native input, a calendar, and a clock.

#### Props

|Prop name|Description|Example values|
|----|----|----|
|calendarClassName|Defines class name(s) that will be added along with "react-calendar" to the main React-Calendar `<div>` element.|<ul><li>String: `"class1 class2"`</li><li>Array of strings: `["class1", "class2 class3"]`</li></ul>|
|clockClassName|Defines class name(s) that will be added along with "react-clock" to the main React-Calendar `<div>` element.|<ul><li>String: `"class1 class2"`</li><li>Array of strings: `["class1", "class2 class3"]`</li></ul>|
|calendarIcon|Defines the content of the calendar button.|<ul><li>String: `"Calendar"`</li><li>React element: `<CalendarIcon />`</li></ul>|
|className|Defines class name(s) that will be added along with "react-datetime-picker" to the main React-DateTime-Picker `<div>` element.|<ul><li>String: `"class1 class2"`</li><li>Array of strings: `["class1", "class2 class3"]`</li></ul>|
|clearIcon|Defines the content of the clear button.|<ul><li>String: `"Clear"`</li><li>React element: `<ClearIcon />`</li></ul>|
|isCalendarOpen|Defines whether the calendar should be opened. Defaults to false.|`true`|
|isClockOpen|Defines whether the clock should be opened. Defaults to false.|`true`|
|locale|Defines which locale should be used by the datetime picker and the calendar. Can be any [IETF language tag](https://en.wikipedia.org/wiki/IETF_language_tag). Defaults to user's browser settings.|`"hu-HU"`|
|maxDate|Defines maximum date that the user can select. Periods partially overlapped by maxDate will also be selectable, although React-DateTime-Picker will ensure that no later date is selected.|Date: `new Date()`|
|maxDetail|Defines the most detailed calendar view that the user shall see. View defined here also becomes the one on which clicking an item in the calendar will select a date and pass it to onChange. Can be "month", "year", "decade" or "century". Defaults to "month".|`"month"`|
|minDate|Defines minimum date that the user can select. Periods partially overlapped by minDate will also be selectable, although React-DateTime-Picker will ensure that no earlier date is selected.|Date: `new Date()`|
|minDetail|Defines the least detailed calendar view that the user shall see. Can be "month", "year", "decade" or "century". Defaults to "century".|`"century"`|
|name|Defines input name. Defaults to "datetime".|`"myCustomName"`|
|onChange|Function called when the user clicks an item on the most detailed view available.|`(value) => alert('New date is: ', value)`|
|returnValue|Defines which dates shall be passed by the calendar to the onChange function and onClick{Period} functions. Can be "start", "end" or "range". The latter will cause an array with start and end values to be passed. Defaults to "start".|`"range"`|
|required|Defines whether date input should be required. Defaults to false.|`true`|
|value|Defines the value of the input.|<ul><li>Date: `new Date()`</li><li>An array of dates: `[new Date(2017, 0, 1), new Date(2017, 7, 1)]`</li></ul>|

### Calendar

DateTimePicker component passes all props to React-Calendar, with the exception of `className` (you can use `calendarClassName` for that instead). There are tons of customizations you can do! For more information, see [Calendar component props](https://github.com/wojtekmaj/react-calendar#props).

### Clock

DateTimePicker component passes all props to React-Clock, with the exception of `className` (you can use `clockClassName` for that instead). There are tons of customizations you can do! For more information, see [Clock component props](https://github.com/wojtekmaj/react-clock#props).

## License

The MIT License.

## Author

<table>
  <tr>
    <td>
      <img src="https://github.com/wojtekmaj.png?s=100" width="100">
    </td>
    <td>
      Wojciech Maj<br />
      <a href="mailto:kontakt@wojtekmaj.pl">kontakt@wojtekmaj.pl</a><br />
      <a href="http://wojtekmaj.pl">http://wojtekmaj.pl</a>
    </td>
  </tr>
</table>
