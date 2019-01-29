# test-cdss-git-training-repo
Test repository for CDSS Git training.
# test-cdss-git-training-repo #

This is a test repository used with the CDSS Git Training!  
Things to keep in mind for Markdown syntax:

- Create a list by using a '-' followed by a space
- Access Atom text editor with the 'atom' keyword followed by the filename
- In Atom, access the Markdown preview with (Ctrl + shift + M)
- Two spaces at the end of a line generates a new line
 
## Contents ##

The repository contains a few folders and files created to demonstrate Git use and various training documentation exercises.

## Maintainer ##

The repository is maintained by Steve Malers.

## Contributing ##

Although this is a public repository, it is just used for training so no contributions are expected.
If contributions were accepted, they would use the Issues or pull requests.

## License ##

[GPL 3.0](https://github.com/smalers/test-cdss-git-training-repo/blob/master/LICENSE)

<div id="iframe container">
 <script async src="//jsfiddle.net/masforce/troj4q5y/5/embed/result/"> </script>
 <script>
  var configurationFile = "https://raw.githubusercontent.com/OpenWaterFoundation/owf-lib-viz-highcharts-js/master/Timeseries/TSTool-Line-Symbology/data-files/config1.json";
var myData = "https://raw.githubusercontent.com/OpenWaterFoundation/owf-lib-viz-highcharts-js/master/Timeseries/TSTool-Line-Symbology/data-prep/2series-example.csv";
$.ajax({
  url: configurationFile,
  async: false,
  dataType: 'json',
  error: function(error) {
    console.log('issue')
  },
  success: function(data) {
    console.log(data)
    //read json configuration properties
    $(function() {
      Highcharts.setOptions(data.Properties);
    });
    $(function() {
      // jQuery command to get/read file from 2series-example.csv
      $.get(myData, function(csvData) {
        var myChart = Highcharts.chart('container', {
          data: {
            csv: csvData // data to be plotted
          }
        });
        //update properties that depend on data
        myChart.update(data.Properties);
      });
    });
  }
})
 </script>
</div>
