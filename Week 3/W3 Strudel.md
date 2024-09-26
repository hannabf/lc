# Week 3 Strudel Experimenting
Still struggling with stacking pitched information for some reason, so made a few fun ostinatos instead. 

Big Steve Reich energy:

```
n ("0 3 6 <8 5 7 8 4 3> 4").scale("C:dorian").sound("zzfx")
  .cpm(90)
  .vowel("<a e>")
  .postgain(1.75)
```

Took the same intervals (adding a 0 and 7 at the start) and changed the key and number of notes per measure based on new notes that were only being played once per cycle (and made it a telephone because it wasn't weird enough already):

```
n ("0 7 0 3 <6 8 5> 7 <8 3> 4").scale("Eb:lydian")
  .sound("gm_telephone")
  .palindrome() 
  .fast(2)
```

And because it's already halloween in my heart:

```
note ("a <g f e d c# d e f a2 b c# d c# d e f>")
  .sound("gm_church_organ")
  .cpm(180)
```