# mad020
basic shape transform loop

![mad020](https://github.com/nicolasbaez/mad020/blob/master/mad020.gif)

```processing
float cantidad;
float radio=height*0.9;
float j=0; // cantidad
float k=0; // rotación
void setup() {
  size(512, 256);
}
void draw() {
  fill(255, 255, 255, 32);
  noStroke();
  rect(0, 0, width, height);
  stroke(random(255), random(255), random(255));
  strokeWeight(4);
  noFill();
  cantidad=int(map(sin(radians(j)), -1, 1, 3, 9));
  beginShape();
  for (int i=0; i<=cantidad; i++) {
    float xx=radio*cos(radians(map(i, 0, cantidad, 0, 360))+k)+width/2;
    float yy=radio*sin(radians(map(i, 0, cantidad, 0, 360))+k)+height/2;
    vertex(xx, yy);
  }
  endShape();
  j+=1;
  k+=map(sin(radians(j)), -1, 1, 0.05, 0.01);
  if (j>=360&&j<720) {
    saveFrame("gif/mad020-######.png");
  }
}
```
