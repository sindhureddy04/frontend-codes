# frontend-codes
CANVAS EXAMPLE

<html>
  <head>
    <style>
      canvas {
        border: 2px solid green;
      }
      body{
        background-color: yellow;
        color:blue;
      }
    </style>
  </head>
  <body> 
    <center>
      <header>
        <h1>Canvas Example</h1>
        <p>Draw on the canvas by clicking and dragging the mouse</p>
      </header>
      <article>
        <h2>Canvas</h2>
        <canvas id="mycanvas"
          width="500"
          height="400"
          onmousedown="startDrawing(event)"
          onmousemove="drawLine(event)"
          onmouseup="stopDrawing(event)">
        </canvas>
      </article>
      <script>
        var canvas = document.getElementById("mycanvas");
        var ctx = canvas.getContext("2d");
        function startDrawing(event) {
          isDrawing = true;
          var x = event.clientX - canvas.offsetLeft;
          var y = event.clientY - canvas.offsetTop;
          ctx.beginPath();
          ctx.moveTo(x,y);
        }
        function drawLine(event){
          if (isDrawing){
             var x = event.clientX - canvas.offsetLeft;
             var y = event.clientY - canvas.offsetTop;
            ctx.lineTo(x,y);
            ctx.stroke();
          }
        }
        function stopDrawing(event){
          isDrawing = false;
        }
      </script>
    </center>
  </body>
</html>
