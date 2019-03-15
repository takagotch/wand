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

with Image() as canvas:
  canvas.evaluate("substract", canvas.quantum_range * 0.07)

with Image() as canvas:
  canvas.evaluate("", canvas.quantum_range * 0.07)




















































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


