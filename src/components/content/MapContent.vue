<template>
    <GmapMap
            :center="{lat:33, lng:-117}"
            :zoom="12"
            map-type-id="terrain"
            style="width: 100%; height: 80vh; display: flex; flex: 1"
    >
        <gmap-info-window :options="infoOptions" :position="infoWindowPos" :opened="infoWinOpen" @closeclick="infoWinOpen=false">
        </gmap-info-window>
        <GmapMarker
                :key="index"
                v-for="(m, index) in markers"
                :position="m.position"
                :clickable="true"
                :draggable="true"
                @click="toggleInfoWindow(m,index)"
        />
    </GmapMap>
</template>

<script>
    export default {
        name: "MapContent",
        data() {
            return {
                infoWindowPos: null,
                infoWinOpen: false,
                currentMidx: null,
                infoOptions: {
                    content: '',
                    //optional: offset infowindow so it visually sits nicely on top of our marker
                    pixelOffset: {
                        width: 0,
                        height: -35
                    }
                },
                center: {
                    lat: 10.0,
                    lng: 10.0
                },
                markers: [{
                    position: {
                        lat: 33.0,
                        lng: -117.0
                    },
                    infoText: '<strong>Marker 1</strong>'
                }, {
                    position: {
                        lat: 33.0,
                        lng: -117.1
                    },
                    infoText: '<strong>Marker 1</strong>'
                }]
            }
        },
        methods: {
            toggleInfoWindow: function (marker, idx) {
                this.infoWindowPos = marker.position;
                this.infoOptions.content = marker.infoText;

                //check if its the same marker that was selected if yes toggle
                if (this.currentMidx == idx) {
                    this.infoWinOpen = !this.infoWinOpen;
                }
                //if different marker set infowindow to open and reset current marker index
                else {
                    this.infoWinOpen = true;
                    this.currentMidx = idx;

                }
            }
        }
    }
</script>

<style scoped>

</style>