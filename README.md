# KML-Map<!DOCTYPE html>
<html>
  <head>
    <title>Client Map Viewer</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
      html, body, #map {
        height: 100%;
        margin: 0;
        padding: 0;
      }
    </style>
    <script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDmJFBZ0IW0ZHEDOttCmhCWQiH0OJf4VSM"></script>
    <script>
      function initMap() {
        const map = new google.maps.Map(document.getElementById("map"), {
          center: { lat: 53.5, lng: -2 }, // UK center-ish
          zoom: 6,
        });

        const kmlUrl = "https://script.google.com/macros/s/AKfycbyBuNK0zq6xrVTSuZ79_zpIu7_poxSJHqf0EOz7IP3MIzlj3nsc5B8d1pr51xQHz8Vo/exec"; // Replace this with your KML URL from Apps Script or Drive

        const kmlLayer = new google.maps.KmlLayer({
          url: kmlUrl,
          map: map,
          preserveViewport: true
        });
      }
    </script>
  </head>
  <body onload="initMap()">
    <div id="map"></div>
  </body>
</html>
