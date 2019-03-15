### wand
---
https://github.com/emcconville/wand

http://docs.wand-py.org/en/0.5.1/

```py
from wand.image import Image
from wand.display import display

with Image(filename='moca-lisa.png') as img:
  print(img.size)
  for r in 1, 2, 3:
    with img.clone() as i:
      i.resize(int(i.width * r * 0.25), int(i.height * r * 0.25))
      i.rotate(90 * r)
      i.save(filename='mona-lisa-{0}.png'.format(r))
      display(i)

from wand.image import Image
from wand.resource import limits

limits['thread'] = 1
with Image(filename='input.tif') as img:
  pass
  
  
with Image(filename='photo.jpg') as photo:
  with open('color_profile.icc', 'rb') as profile:
    photo.profiles['icc'] = profile.read()

with Image(width=1, height=1, background=Color("gray5")) as canvas:
  canvas.evaluate("substract", canvas.quantum_range * 0.07)

with Image(width=1, height=1, background=Color("gray5")) as canvas:
  canvas.evaluate("substract", canvas.quantum_range * 0.07)


from wand.version import MAGICK_VERSION_NUMBER
from wand.image import Image

with Image(filename="wizard:") as img:
  image_type = "truecoloralpha"
  if MAGICK_VERSION_NUMBER < 0x700:
    image_type = "truecolormatte"
  img.type = image_type

with Image(width=1, height=1, background=Color("gray5")) as canvas:
  canvas.evaluate("substract", canvas.quantum_range * 0.07)
  canvas.clamp()
  print(canvas[0, 0])

from wand.image import Image, CHANNELS
from wand.api import library

with Image(filename="rose:") as img:
  active_mask = CHANNELS["red"] | CHANNELS["green"]
  previous_mask = library.MagickSetImageChannelMask(img.wand, active_mask)
  img.evaluate("rightshift", 1)
  library.MagickSetImageChannelMask(img.wand, previous_mask)
  img.save(filename="blue_rose.png")














































```

```
apg-get install libmagicwand-dev
pip install Wand

pip install Wand
git clone git://github.com/emcconville/wand.git
cd wand/
python setup.py install
```

```
```


