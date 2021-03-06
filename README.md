# react-expandable-table

## Installation

The package can be installed via npm by running: `npm install`, or `npm i` for brevity.

## Usage

```jsx
import Table from 'react-expandable-table';

...

<Table columns={[{ key: 'red' }, { key: 'blue' }]} dataSource={[{ red: true, blue: false }, { red: false, blue: true }]} />
```

## API

### Props

<table class="table table-bordered table-striped">
  <thead>
    <tr>
      <th style="width: 125px;">Name</th>
      <th style="width: 75px;">Type</th>
      <th>Default</th>
      <th style="width: 75px;">Required</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>columns</td><td>arrayOf(shape)</td><td>[]</td><td>false</td><td>See column props below</td></tr><tr><td>dataSource</td><td>arrayOf(object)</td><td>[]</td><td>false</td><td>An array of objects, each containing key-value pairs, where the keys correspond to column keys</td></tr><tr><td>emptyText</td><td>string</td><td>'No Data'</td><td>false</td><td>Text to be displayed when dataSource is empty or undefined</td></tr><tr><td>expandButtonRender</td><td>func</td><td></td><td>false</td><td>Optional custom render to be used for the row expand button.
Make sure your custom node calls the provided onClick function.
Optionally, you can also use the provided isExpanded boolean if you'd like to conditionally render based on the current row's isExpanded state

Function({ onClick, isExpanded }):ReactNode|[ReactNode]</td></tr><tr><td>expandCellWidth</td><td>number</td><td>50</td><td>false</td><td>The [fixed] width (in pixels) of the expand row button cell.</td></tr><tr><td>isBordered</td><td>bool</td><td>false</td><td>false</td><td>If true, the table will be styled with borders.</td></tr><tr><td>onRowClick</td><td>func</td><td></td><td>false</td><td>Function to be invoked when a row is clicked.

Function(rowData, rowIndex):void</td></tr><tr><td>onRowExpand</td><td>func</td><td></td><td>false</td><td>Function to be invoked when a row expand icon is clicked
The expand icon will be included by default if you provide an onRowExpand function.

Function(rowData, rowIndex):ReactNode|[ReactNode]</td></tr>

  </tbody>
</table>

### Column Props

<table class="table table-bordered table-striped">
  <thead>
    <tr>
      <th style="width: 125px;">Name</th>
      <th style="width: 75px;">Type</th>
      <th>Default</th>
      <th style="width: 75px;">Required</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>key</td><td>string</td><td>true</td><td>false</td><td>Unique identifier used to identify this column.</td></tr>
    <tr><td>dataTooltip</td><td>func</td><td></td><td>false</td><td>Function to generate a custom tooltip string for the specific data cell. If not provided, the tooltip will default to `cellData` if it can be parsed into a string. `Function(cellData, rowData):string`</td></tr>
    <tr><td>render</td><td>func</td><td></td><td>false</td><td>Optional custom render to be used for the column data cell. `Function(cellData, rowData, rowIndex):ReactNode|[ReactNode]`</td></tr>
    <tr><td>title</td><td>node</td><td></td><td>false</td><td>Optional custom node to be used for the column title.</td></tr>
    <tr><td>titleTooltip</td><td>string</td><td></td><td>false</td><td>Optional tooltip for the column's title (th), defaults to `column.title` (if string parsable)</td></tr>
    <tr><td>width</td><td>number</td><td></td><td>false</td><td>Optional number to be used to represent what percentage of the total width this column should span. Similar to the css `flex-grow` property.</td></tr>
  </tbody>
</table>

## Development

First, install necessary dependencies:
`npm i`

Then start up the [styleguide](https://github.com/styleguidist/react-styleguidist) server on [localhost:6060](http://localhost:6060):
`npm start`

You can edit or add to the styleguide examples in `Table.md`.

To run the test suite:
`npm run test`
or
`npm run test:watch`
