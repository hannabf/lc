 Week 9: Second TidalCycles Patch

This time, with samples:

```
-- Drums
d1 $ slice 8 "[<0*6 0*2> 3*4 2 4] [4 .. 7]" $ sound "breaks165"
  # legato 1
  # squiz "1.25"

d2 $ n "[3*4 5 2 2] [2 2 5 2]" # s "lt"
  # gain 0.65
  # detune 9


-- Strings sample from Heitor Villa-Lobos String Quartet no. 5
d3 $ fast 5 $ randslice 64 $ s "hvl:10"
  # room 0.6
  # leslie "0.25"
  # djf "0.75"
  # pan (slow 10 cosine)

-- aaaannnddyyyy
d4 $ n "3*4 5 2 6 7 1 1 0" # s "kurt"
  # decay "[1 | 0.2]/4"
  # pan (slow 10 sine)
  # room 0.4
  # gain 0.7 
```

It took a second to figure out downloading my own samples, but having them in there the possabilites feel so endless. I started off a bit straightforward for this one because I mostly added one-shot vocal samples or really long samples like this Villa-Lobos string quartet I chopped up, but I definitely want to experiment with adding more instrument-based samples and using those. I also wondered if there was a way to go between notes in a folder of samples like the "kurt" sample I pulled from the TidalCycles samples? Lots of fun things to experiment with for the final for sure.