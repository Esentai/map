<template></template>
<script>
export default {
  inject: ["google", "map"],
  props: {
    position: Object,
  },
  data(){
    return {
      marker: null,

    }
  },
  mounted(){
    const { Marker } = this.google.maps;
    this.marker = new Marker({
      position: {
        lat: parseFloat(this.position.lat),
        lng: parseFloat(this.position.lng),
      },
      icon:{
        url: this.position.icon,
        scaledSize: new google.maps.Size(40, 40)
      },
      map: this.map,
      title: "Child marker!",
    });
    this.marker.addListener( 'click', function() {
      console.log("Salem Alem");
    });
  }
}
</script>

