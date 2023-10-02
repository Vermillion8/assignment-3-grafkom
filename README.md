# Grafika Komputer - A | Assignment 3 | Thalent Athalla Razzaq | 5025211101

## Make a 2D square

![alt text](https://github.com/Vermillion8/assignment-3-grafkom/blob/master/images/triangle.png?raw=true)

```glsl
function draw() {

      gl.clearColor(0, 0, 0, 1);  // specify the color to be used for clearing
      gl.clear(gl.COLOR_BUFFER_BIT);  // clear the canvas (to black)

      /* Set up values for the "coords" attribute */

      let coords = new Float32Array([-0.5, -0.5, -0.5, 0.5, 0.5, 0.5]);

      gl.bindBuffer(gl.ARRAY_BUFFER, bufferCoords);
      gl.bufferData(gl.ARRAY_BUFFER, coords, gl.STREAM_DRAW);
      gl.vertexAttribPointer(attributeCoords, 2, gl.FLOAT, false, 0, 0);
      gl.enableVertexAttribArray(attributeCoords);

      /* Set up values for the "color" attribute */

      let color = new Float32Array([0, 1, 0, 0, 0, 1, 1, 0, 0]);

      gl.bindBuffer(gl.ARRAY_BUFFER, bufferColor);
      gl.bufferData(gl.ARRAY_BUFFER, color, gl.STREAM_DRAW);
      gl.vertexAttribPointer(attributeColor, 3, gl.FLOAT, false, 0, 0);
      gl.enableVertexAttribArray(attributeColor);

      /* Draw the triangle. */

      gl.drawArrays(gl.TRIANGLES, 0, 3);

      let coords2 = new Float32Array([-0.5, -0.5, 0.5, 0.5, 0.5, -0.5]);
      gl.bindBuffer(gl.ARRAY_BUFFER, bufferCoords);
      gl.bufferData(gl.ARRAY_BUFFER, coords2, gl.STREAM_DRAW);

      let color2 = new Float32Array([0, 1, 0, 1, 0, 0, 1, 1, 1]);

      gl.bindBuffer(gl.ARRAY_BUFFER, bufferColor);
      gl.bufferData(gl.ARRAY_BUFFER, color2, gl.STREAM_DRAW);

      gl.drawArrays(gl.TRIANGLES, 0, 3);


    }
```

## Make a 3D cube

![alt text](https://github.com/Vermillion8/assignment-3-grafkom/blob/master/images/cube_all_sides.png?raw=true)

```glsl
function draw() {
      gl.clearColor(0, 0, 0, 1);
      gl.clear(gl.COLOR_BUFFER_BIT | gl.DEPTH_BUFFER_BIT);

      /* Draw the six faces of a cube, with different colors. */

      drawPrimitive(gl.TRIANGLE_FAN, [0, 1, 0, 1], [-0.5, -0.5, -0.5, -0.5, 0.5, -0.5, 0.5, 0.5, -0.5, 0.5, -0.5, -0.5]); // Front
      drawPrimitive(gl.TRIANGLE_FAN, [1, 0, 0, 1], [-0.5, 0.5, 0.5, 0.5, 0.5, 0.5, 0.75, 0.75, 0.5, -0.25, 0.75, 0.5]); // Top
      drawPrimitive(gl.TRIANGLE_FAN, [0, 0, 1, 1], [0.75, -0.25, 0.5, 0.5, -0.5, 0.5, 0.5, 0.5, 0.5, 0.75, 0.75, 0.5]); // Right
      drawPrimitive(gl.TRIANGLE_FAN, [1, 1, 0, 1], [-0.5, -0.5, 0.5, 0.5, -0.5, 0.5, 0.75, -0.25, 0.5, -0.25, -0.25, 0.5]); // Bottom
      drawPrimitive(gl.TRIANGLE_FAN, [1, 0, 1, 1], [-0.25, 0.75, 0.5, -0.5, 0.5, 0.5, -0.5, -0.5, 0.5, -0.25, -0.25, 0.5]); // Left
      drawPrimitive(gl.TRIANGLE_FAN, [0, 1, 1, 1], [-0.25, 0.75, 0.5, -0.25, -0.25, 0.5, 0.75, -0.25, 0.5, 0.75, 0.75, 0.5]); // Back

    }
```

- Cube with no front

![alt text](https://github.com/Vermillion8/assignment-3-grafkom/blob/master/images/cube_no_front.png?raw=true)

- Cube with no top

![alt text](https://github.com/Vermillion8/assignment-3-grafkom/blob/master/images/cube_no_top.png?raw=true)