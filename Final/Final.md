Final TidalCycles Patch

```
setcps (0.55)


---------------------- Drums
-- HH
d1 $ qtrigger $ s "hh(5, 8)"
  # amp envL
  # room 0.4
  # gain 0.75

-- Break
d1 $ qtrigger $ slice 8 "[<0*6 0*2> 3*4 2 4] [4 .. 7]" $ sound "breaks125"
  # legato 1
  # gain 0.9

-- Break + K
d1 $ qtrigger $ stack [
  s "dr_few*4"
    # amp envL
    # shape 0.7
    # gain 0.65,
  slice 8 "[<0*6 0*2> 3*4 2 4] [4 .. 7]" $ sound "breaks125"
    # legato 1
  ]

-- Beeps
d1 $ qtrigger $ slice 8 "[<0*6 0*2> 3*4 2 4] [4 .. 7]" $ sound "feelfx"
    # legato 1

-- Beeps and Kick
d1 $ qtrigger $ stack [
    s "dr_few*4"
      # amp envL
      # shape 0.7
      # gain 0.625,
    slice 8 "[<0*6 0*2> 3*4 2 4] [4 .. 7]" $ sound "feelfx"
      # legato 1
    ]

-- Beeps Kick and Break
d1 $ qtrigger $ stack [
  s "dr_few*4"
    # amp envL
    # shape 0.8
    # gain 0.65,
  slice 8 "[<0*6 0*2> 3*4 2 4] [4 .. 7]" $ sound "feelfx"
    # legato 1,
  slice 8 "[<0*6 0*2> 3*4 2 4] [4 .. 7]" $ sound "breaks125"
    # legato 1
  ]



---------------------- Andyyyyy
d2 $ qtrigger $ n "3*4 5 2 6 7 1 1 0" # s "kurt"
  # decay "[1 | 0.2]/4"
  # pan (slow 10 sine)
  # room 0.4
  # gain 0.85

d2 $ qtrigger $ n "3*2 5 6 8*3" # s "kurt"
  # decay "[1 | 0.2]/4"
  # pan (slow 10 sine)
  # room 0.4
  # gain 0.85

d2 $ qtrigger $ n "3*4 ~ ~ ~ ~ ~ ~  ~" # s "kurt"
  # decay "[1 | 0.2]/4"
  # pan (slow 10 sine)
  # room 0.4
  # gain 0.85

-- yippeeeeeee
d2 $ qtrigger $ slice 8 "[<2*6 3*2> 3*4 2 4*2] [4 .. 7]" $ sound "yippee"
  # legato 1
  # hpf 1500
  # leslie "0.75"
  # pan (slow 10 sine)
  # gain 0.9



---------------------- fax machine adjacent
d3 $ qtrigger $ slice 8 "[<0*4 1*4> 3*4 2 4] [4 .. 7]" $ sound "scarychords:02"
  # legato 1
  # room 0.3
  # leslie "0.25"
  # djf "0.75"



---------------------- Msc Vox
d4 $ qtrigger $ slice 8 "[<0*6 0*2> 3*4 2 4] [4 .. 7]" $ sound "alphabet"
  # legato 1
  # pan (slow 10 cosine)

d4 $ qtrigger $ slice 8 "[0 3 2 4] [2 .. 7]" $ sound "alphabet"
  # legato 1
  # leslie "0.25"
  # pan (slow 10 cosine)
  # gain 0.9

d4 $ qtrigger $ slice 8 "[<0*6 0 ~> 3*4 ~ ~] [4 .. 7]" $ sound "alphabet"
  # legato 1
  # pan (slow 10 cosine)

-- Ernie
d4 $ qtrigger $ slow 2 $ sound "ernie"
  # shape 0.5
  # leslie "0.2"
  # room 0.2



---------------------- Vox
once $ sound "vox:01"
  # room 0.7
  # gain 0.8
  # pan (sine)

-- try this
once $ sound "gauntlet:13"
  # shape 0.35
  # room 0.7

-- heroic effort
once $ sound "gauntlet:12"
  # shape 0.375
  # room 0.7

```

Based off of one of my assignments from a couple weeks ago, I mainly was aiming to figure out the best was of organizing my set to trigger a bunch of stuff ad-lib. My nemesis in TidalCycles is still muting a group so I wanted to do something a little more free-flowing, so this weird techno/trance thing is where we landed. I also wanted to add some goofy one-shots at the end because I thought it would be fun