<script setup>
import {SmithchartComponent as EjsSmithchart, SeriesCollectionDirective as ESeriesCollection,
        SeriesDirective as ESeries, SmithchartLegend, TooltipRender
} from '@syncfusion/ej2-vue-charts';
import {provide} from 'vue';

provide('smithchart',[SmithchartLegend, TooltipRender]);

const points = [
{ resistance: 20, reactance: -50 }, { resistance: 10, reactance: -10 },
{ resistance: 9, reactance: -4.5 }, { resistance: 8, reactance: -3.5 },
{ resistance: 7, reactance: -2.5 }, { resistance: 6, reactance: -1.5 },
{ resistance: 5, reactance: -1 }, { resistance: 4.5, reactance: -0.5 },
{ resistance: 3.5, reactance: 0 }, { resistance: 2.5, reactance: 0.4 },
{ resistance: 2, reactance: 0.5 }, { resistance: 1.5, reactance: 0.5 },
{ resistance: 1, reactance: 0.4 }, { resistance: 0.5, reactance: 0.2 },
{ resistance: 0.3, reactance: 0.1 }, { resistance: 0, reactance: 0.05 }
];
const dataSource = [
{ resistance: 10, reactance: 25 }, { resistance: 8, reactance: 6 },
{ resistance: 6, reactance: 4.5 }, { resistance: 4.5, reactance: 2 },
{ resistance: 3.5, reactance: 1.6 }, { resistance: 2.5, reactance: 1.3 },
{ resistance: 2, reactance: 1.2 }, { resistance: 1.5, reactance: 1 },
{ resistance: 1, reactance: 0.8 }, { resistance: 0.5, reactance: 0.4 },
{ resistance: 0.3, reactance: 0.2 }, { resistance: 0, reactance: 0.15 }
];
const title = {text:'Impedance Transmission'};
const marker = {visible: true, dataLabel:{visible: true}};
const marker2={visible: true};
const legendSettings = {visible: true};
const tooltip = {visible: true};

</script>

<template>
<ejs-smithchart :title="title" :legendSettings="legendSettings">
  <e-seriesCollection>
    <e-series :points="points" :marker="marker"
    name="Transmission1" :tooltip="tooltip"></e-series>
    <e-series :dataSource="dataSource" resistance="resistance"
    reactance="reactance" :marker="marker2" name="Transmission2"
    :tooltip="tooltip"></e-series>
  </e-seriesCollection>
</ejs-smithchart>
</template>

<style scoped>

</style>
