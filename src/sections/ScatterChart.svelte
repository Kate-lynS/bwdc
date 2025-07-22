<script>
  import { onMount } from 'svelte';
  import Highcharts from 'highcharts';
  // Optional: Enable exporting if needed
  // import Exporting from 'highcharts/modules/exporting';
  // Exporting(Highcharts);

  onMount(() => {
    Highcharts.chart(
      
      {
        chart: {
          type: 'scatter',
          zoomType: 'xy'
        },
        title: {
          text: 'Uninsured vs. University Education by Race'
        },
        subtitle: {
          text: 'Data from non-expansion states (BWDC/KFF)'
        },
        xAxis: {
          title: {
            text: '% with University Degree'
          },
          startOnTick: true,
          endOnTick: true,
          showLastLabel: true,
          gridLineWidth: 1
        },
        yAxis: {
          title: {
            text: '% Uninsured'
          },
          gridLineWidth: 1,
          min: 0
        },
        legend: {
          enabled: false
        },
        tooltip: {
          pointFormat: '<b>{point.name}</b><br>Education: {point.x}%<br>Uninsured: {point.y}%'
        },
        series: [{
          name: 'Race Groups',
          colorByPoint: true,
          data: [
            { name: 'White', x: 35, y: 9.6 },
            { name: 'Hispanic', x: 20, y: 24.6 },
            { name: 'Black', x: 25, y: 12.9 },
            { name: 'Asian', x: 50, y: 9.2 },
            { name: 'AIAN', x: 15, y: 17.1 }
          ]
        }]
      }
    );
  });
</script>

<div id="scatter-container"></div>

<style>
  #scatter-container {
    width: 100%;
    height: 400px;
    margin-top: 2rem;
  }
</style>
