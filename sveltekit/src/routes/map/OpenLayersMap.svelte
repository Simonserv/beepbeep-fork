<script lang="ts">
    import Map from "ol/Map";
    import View from "ol/View";
    import TileLayer from "ol/layer/Tile";
    import XYZ from "ol/source/XYZ";
    import { onMount } from "svelte";

    const enum map_themes {
        LIGHT_MODE =  "https://{a-c}.basemaps.cartocdn.com/light_all/{z}/{x}/{y}{r}.png",
        DARK_MODE = "https://{a-c}.basemaps.cartocdn.com/dark_all/{z}/{x}/{y}{r}.png"
    };

    let mapElement: HTMLElement;
    let mountedMap: Map;
    onMount(() => {
        mountedMap = new Map({
            target: mapElement,
            layers: [
                new TileLayer({
                    source: new XYZ({
                        url: map_themes.DARK_MODE,
                    }),
                }),
            ],
            view: new View({
                center: [0, 0],
                zoom: 2,
            }),
        });
    });
</script>

<div bind:this={mapElement} 
    class="relative top-0 left-0 h-dvh w-screen" />
