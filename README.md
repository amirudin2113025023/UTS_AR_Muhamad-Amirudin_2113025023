<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AR Website Background</title>
    <script src="https://aframe.io/releases/1.2.0/aframe.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/ar.js"></script> 
    <script>
      AFRAME.registerComponent('move-object', {
        init: function () {
          var el = this.el;
          var step = 0.1; 

          window.addEventListener('keydown', function (event) {
            switch (event.key) {
              case 'ArrowUp':
                el.object3D.position.y += step;
                break;
              case 'ArrowDown':
                el.object3D.position.y -= step;
                break;
              case 'ArrowLeft':
                el.object3D.position.x -= step;
                break;
              case 'ArrowRight':
                el.object3D.position.x += step;
                break;
            }
          });
        }
      });
    </script>
</head>
<body>
    <a-scene embedded arjs="sourceType: webcam;">
        <a-box move-object position="0 1.6 -3" rotation="0 45 0" width="4" height="2" depth="2" color="orange">
            <a-text value="Dinding" position="1 0.25 1.25" align="center" color="black"></a-text>
        </a-box>

        <a-cone move-object position="0 3.6 -3" rotation="0 45 0" radius-bottom="3.5" radius-top="0" height="3" color="brown">
            <a-text value="Atap" position="0 1.9 0" align="center" color="black"></a-text>
        </a-cone>

        <a-box move-object position="0 1.13 -1.5" rotation="0 45 0" width="0.7" height="1" depth="1.0" color="brown">
            <a-text value="Pintu" position="0 0.5 0.5" align="center" color="black"></a-text>
        </a-box>
        <a-box move-object position="0 1.13 -1.5" rotation="0 45 0" width="0.1" height="0.1" depth="1.0" color="black"></a-box>

        <a-box move-object position="0 1.40 -3.0" rotation="0 45 0" width="1" height="0.5" depth="2.5" color="blue">
            <a-text value="Jendela" position="0 0.25 1.25" align="center" color="black"></a-text>
        </a-box>
 
        <a-cylinder move-object position="1.5 4 -3" rotation="0 45 0" radius="0.1" height="0.5" color="gray">
            <a-text value="Cerobong Asap" position="0 0.25 0.25" align="center" color="black"></a-text>
        </a-cylinder>
   
        <a-text move-object value="Muhamad Amirudin (2113025023)" position="4 0.6 -4" rotation="0 45 0" align="center" color="black" font="https://cdn.aframe.io/fonts/Exo2Bold.fnt" scale="2 2 2"></a-text>
    </a-scene>
</body>
</html>
