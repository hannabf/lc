# Strudel + Hydra Performance Reflection

## Full Code:


```
samples('github:yaxu/clean-breaks')
await initHydra()

// Visuals
s0.initCam() //initialize webcam as external source 's0'

src(s0)
    .layer(gradient().g())
    .color(-1, 1, 1.2)
    .out (o0) // Camera output o0

// licensed with CC BY-NC-SA 4.0 https://creativecommons.org/licenses/by-nc-sa/4.0/
// by Olivia Jack (https://ojack.github.io)
 osc(100, 0.01, 1.4)
	.rotate(0, 0.1)
	.mult(osc(10, 0.1).modulate(osc(10).rotate(0, -0.1), 1))
	.color(2.5,0.91,0.39)
    .blend(o0)
    .out(o1) // Camera output -1

// licensed with CC BY-NC-SA 4.0 https://creativecommons.org/licenses/by-nc-sa/4.0/
// by Olivia Jack
osc(6, 0, 0.8)
  .color(1.14, 0.6,.80)
.rotate(0.92, 0.3)
.pixelate(20, 10)
  .mult(osc(40, 0.03).thresh(0.4).rotate(0, -0.02))
.modulateRotate(osc(20, 0).thresh(0.3, 0.6), () => 0.1 + mouse.x * 0.002)
  .blend(o0)
  .out (o2) // Camera output 02

// licensed with CC BY-NC-SA 4.0 https://creativecommons.org/licenses/by-nc-sa/4.0/
//filet mignon AFALFL (instagram/a_f_alfl)
osc(100,-0.0018,0.17).diff(osc(20,0.00008).rotate(Math.PI/0.00003))
.modulateScale(noise(1.5,0.18).modulateScale(osc(13).rotate(()=>Math.sin(time/22))),3)
.color(11,0.5,0.4, 0.9, 0.2, 0.011, 5, 22,  0.5, -1).contrast(1.4)
.add(src(o0).modulate(o0,.04),.6, .9)
.invert().brightness(0.0003, 2).contrast( 0.5, 2, 0.1, 2).color(4, -2, 0.1)
.modulateScale(osc(2),-0.2, 2, 1, 0.3)
 .posterize(200) .rotate(1, 0.2, 0.01, 0.001)
 .color(22, -2, 0.5, 0.5, 0.0001,  0.1, 0.2, 8).contrast(0.18, 0.3, 0.1, 0.2, 0.03, 1) . brightness(0.0001, -1, 10)
  .diff(o1)
   .layer(gradient().g())
   .blend(o0)
   .out(o3)// Camera output o3




//Visuals Control
render(o0)

// Drums

_$: s("impeach/1.25")
  .splice(8, "<0 0 2 1 4*2 5 6 [2 4]>*10") //main groove DT
//  .splice(8, "<0 0 2 1 4*2 5 6 [6  7]>*5") //main groove HT
//  .splice (8, "<5 5 5 5> *5") .lpf(800) //build
//  .splice(8, "<0 0 2 1 4*3 5 6 [6*2] 0? [0 2]? 2 1 4 5 6 [6 1 7]>*10") //idk
  .cut(1).rarely(ply("2"))
  .lpf(slider(100, 100, 10000, 1))


// Chords
_$: chord("<Cm9 Ab^7 Dm7b5 G7> *.5").layer(
   x=>x.anchor("F4").voicing()
  ,x=>x.rootNotes("<2 1 2 -5>")
  ).struct("[2]") 
  .lpa(".25")
  .cpm(75)
  .lpf(slider(100, 100, 5000, 1))

// Bass
_$: note("<c2 ab1 d2 g1> *.5").s("square")
  .struct("[2]")
  .cpm(75)
  .attack(.05).lpf(1000)

```

## Reflections:
For this performance my main goal was to create a really contained but still versatile code that would be easy to manage, both visually and for performance. I'm really excited to see how everyone formatted their code for inspiration on organization, because I have a tendency to let Massive Lines Of Code freak me out a little bit, and I was trying by absolute best to keep everything I wanted to control on screen. This did mean cutting out a lot of the information visually (haha) for the visuals, but I think for transparency to the audience and to properly credit the artists whose code I used that could easily be solved by scrolling through the entire code at the start and end of a performance.
I also initially was a week or so behind having been sick and was sort of dreading rehearsing this week prior, but I actually found I like the rehearsal and performing aspect almost more than the making of the song itself. It's obviously not as quick yet as triggering a bunch of Ableton Live scenes, but it's sort of a fun challenge to make sure everything is properly commented out and readjusted before hitting the update button in time. It adds and excitement, and also really makes me appreciate my elemantary school typing lessons in retrospect.
Overall I'm really starting to taste the full potential of a performance done in this style, and I'm really excited to learn more techniques and try to do more live coding performances!