<h1 align="center"> react-native-calendar-strip </h1>
<div align="center">
  <strong> Easy to use and visually stunning calendar component for React Native.</strong>
</div>
<div align="center">
  <a href="https://www.npmjs.com/package/react-native-calendar-strip">Fork of https://www.npmjs.com/package/react-native-calendar-strip</a>
</div>
<br>
<strong>Modified UI -> Arrows moved to top right</strong><br><br>

<img width="332" alt="Screenshot 2023-08-07 at 3 43 54 PM" src="https://github.com/maneeswarmutyala/react-native-calendar-strip/assets/44763136/03055221-d6dd-4108-a4be-e049b243d18a">

<strong>Code Changes</strong>
<p> Passing Component State as prop `parentProps` to header component from Strip component</p>

```Javascript
<CalendarHeader
          calendarHeaderFormat={this.props.calendarHeaderFormat}
          calendarHeaderContainerStyle={this.props.calendarHeaderContainerStyle}
          calendarHeaderStyle={this.props.calendarHeaderStyle}
          onHeaderSelected={this.props.onHeaderSelected}
          weekStartDate={this.state.weekStartDate}
          weekEndDate={this.state.weekEndDate}
          fontSize={this.state.monthFontSize}
          allowHeaderTextScaling={this.props.shouldAllowFontScaling}
          headerText={this.props.headerText}
          parentProps={this.props}
          getPreviousWeek={this.getPreviousWeek}
          getNextWeek={this.getNextWeek}
          parentState={this.state}
    />
```

<p>In Header, added the arrows</p>

```Javascript
       <View style={{ display: 'flex', flexDirection: 'row', justifyContent:'space-between', width:50}}>
            <WeekSelector
              controlDate={this.props.parentProps.minDate}
              iconComponent={this.props.parentProps.leftSelector}
              iconContainerStyle={this.props.parentProps.iconContainer}
              iconInstanceStyle={this.props.parentProps.iconLeftStyle}
              iconStyle={this.props.parentProps.iconStyle}
              imageSource={this.props.parentProps.iconLeft}
              onPress={this.props.getPreviousWeek}
              weekStartDate={this.props.parentState.weekStartDate}
              weekEndDate={this.props.parentState.weekEndDate}
              size={this.props.parentState.selectorSize}
            />
            <WeekSelector
              controlDate={this.props.parentProps.minDate}
              iconComponent={this.props.parentProps.rightSelector}
              iconContainerStyle={this.props.parentProps.iconContainer}
              iconInstanceStyle={this.props.parentProps.iconRightStyle}
              iconStyle={this.props.parentProps.iconStyle}
              imageSource={this.props.parentProps.iconRight}
              onPress={this.props.getNextWeek}
              weekStartDate={this.props.parentState.weekStartDate}
              weekEndDate={this.props.parentState.weekEndDate}
              size={this.props.parentState.selectorSize}
            />
          </View>
```
