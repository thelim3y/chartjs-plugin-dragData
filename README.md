# chartjs-plugin-dragData.js

A plugin for Chart.js >= 2.4.0

Makes data points draggable.

![Drag Data Animation](https://chrispahm.github.io/chartjs-plugin-dragData/assets/chartjs-plugin-dragData.gif)

[Online demo single Y-Axis](https://chrispahm.github.io/chartjs-plugin-dragData/), [dual Y-Axis](https://chrispahm.github.io/chartjs-plugin-dragData/dualAxis.html).
## Configuration

To make (line chart) data points draggable, simply add ```dragData: true``` to the config section of the chart instance.
Additionally, individual event listeners can be specified as follows:

```javascript
{
	...
	dragData: true,
	onDragStart: function (event, element) {

	},
	onDrag: function (event, datasetIndex, index, value) {

	},
	onDragEnd: function (event, datasetIndex, index, value) {

	}
}
```
When dragging data points towards the outer boundaries of the y-axis, one may experience unexptected (fast) changes to the y-axis scale.
Therefore, depending on the use case, it may be recommended to fix the y-scale using similar options as follows (especially on small charts):

```javascript
options: {
	scales: {
		yAxes: [{
				ticks: {
						max: 25,
						min: 0
				}
		}]
	},
	...
```

## Installation

To install via npm:

```
npm install chartjs-plugin-dragdata --save
```

Or, download a release archive file from the dist folder.

## Contributing

Please feel free to submit an issue or a pull request!

## License

chartjs-plugin-dragdata.js is available under the [MIT license](http://opensource.org/licenses/MIT).
