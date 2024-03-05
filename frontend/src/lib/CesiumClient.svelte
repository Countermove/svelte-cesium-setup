<script>
  import { onMount } from 'svelte';
  import * as Cesium from 'cesium';
  import '../../node_modules/cesium/Build/Cesium/Widgets/widgets.css';

  const CESIUM_ION_TOKEN = import.meta.env.VITE_CESIUM_TOKEN;
  Cesium.Ion.defaultAccessToken = CESIUM_ION_TOKEN;

  let viewer;

  onMount(async () => {
    viewer = new Cesium.Viewer('cesiumContainer', {
      terrainProvider: await Cesium.createWorldTerrainAsync(),
    });
  });
</script>

<div id="cesiumContainer"></div>