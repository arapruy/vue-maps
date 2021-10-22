<template>
  <div :id="svgId" class="svg-container"></div>
</template>
<script>

import corrientesMap from "../assets/corrientesMap.js"
export default {
  name: "CorrientesMap",
  data: function () {
    return {
      svgId: "corrientesMap",
      mapAttr: {
        viewBoxWidth: 1106,
        viewBoxHeight: 1106,
        imageWidth: 1106,
        imageHeight: 500,
      },
      svgContainer: null
    }
  },
  mounted: function () {
    this.generateVenueMap()
  },
  methods: {
    generateVenueMap: function () {
      const vue = this;
      const mapData = corrientesMap.g.path
      const svgContainer = vue.$svg("corrientesMap").size('100%', '100%').viewbox(-200, 0, vue.mapAttr.viewBoxWidth, vue.mapAttr.viewBoxHeight);
      vue.svgContainer = svgContainer;
      mapData.forEach((pathObj) => {
        vue.generatePath(svgContainer, pathObj);
      })
    },
    generatePath: function (svgCont, pathObj) {
      const vue = this;

      const attrs = {
        'fill': "#689F38",
        'stroke': "white",
        'stroke-width': 2,
        'title': pathObj["-title"],
        'map-id': pathObj["-id"],
      };
      const element = svgCont.path(pathObj["-d"]).attr(attrs);
      element.click(function () {
        const mapId = this.node.attributes["map-id"].value;
        const title = this.node.attributes["title"].value;
        vue.$emit("map-clicked", {mapId, title});
      })

    }
  }

}
</script>