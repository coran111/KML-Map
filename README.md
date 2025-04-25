<!DOCTYPE html>
<html>
  <head>
    <title>KML Map Viewer</title>
    <meta charset="utf-8" />
    <style>
      html, body, #map {
        height: 100%;
        margin: 0;
        padding: 0;
      }
    </style>
  </head>
  <body>
    <div id="map"></div>
    <script>
      function initMap() {
        const map = new google.maps.Map(document.getElementById("map"), {
          center: { lat: 53.8, lng: -1.5 },
          zoom: 6,
        });

        // Array of KML URLs
        const kmlFiles = [
          "https://drive.google.com/file/d/1tspWQyZ1M_e66nCdLSwrgNJvAwdJnhIM/view?usp=drive_link",
          "https://drive.google.com/file/d/15HDBCf9-HBPXXvwcU9cMTJmcq3zz8S-2/view?usp=drive_link",
          "https://drive.google.com/file/d/1TkQ3lGQaoEwa9rwbu7SmmyR-CgUkXd1Q/view?usp=sharing",
          "https://drive.google.com/file/d/1g5Du6xJosan3IEMJXwRqGJWZyryLWAPp/view?usp=sharing",
          "https://drive.google.com/file/d/1a7juykSEXIGOb27rz8M91boP57X6QfX2/view?usp=sharing",
          "https://drive.google.com/file/d/1Pnc0BNy1tsGDfyUt_H6VAlsY8eL5v52I/view?usp=sharing"
        ];

        // Load each KML file as a layer
        kmlFiles.forEach((url, index) => {
          new google.maps.KmlLayer({
            url: url,
            map: map,
            preserveViewport: false,
            zIndex: index + 1, // Ensure layers stack in the order you want
          });
        });
      }
    </script>
    <script async
      src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDmJFBZ0IW0ZHEDOttCmhCWQiH0OJf4VSM&callback=initMap">
    </script>
  </body>
</html>
