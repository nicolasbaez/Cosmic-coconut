# Cosmic-coconut
Blooop

![buh](https://github.com/nicolasbaez/Cosmic-coconut/blob/main/xp027.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
k = h = 255;
draw = (_) => {
  rotateX(1);
  rotateY(0.5);
  clear();
  directionalLight(0, h, h, 1, 1, 0);
  stroke(h, 0, 0);
  for (j = 0; j < 50; j++)
    for (i = 0; i < 50; i++) {
      x = i * 50;
      y = j * 50;
      push();
      translate(x - h, y - h, sin(noise(i, j, k)) * 30);
      sphere(noise(x, y) * 99);
      pop();
    }
  k -= 0.02;
};

keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp027.gif", 314, { delay: 0, units: "frames" });
  }
};
