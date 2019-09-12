### pygame
---
https://github.com/pygame/pygame

http://www.pygame.org/news.html

```py
// test/cursors_test.py
import unittest
from pygame.test.test_utils import fixture_path
import pygame

class CursorsModuleTest(unittest.TestCase):
  def todo_test_compile(self):
    self.fail()
    
  def test_load_xbm(self):
    cursorfile = fixture_path(r"xbm_cursors/white_sizing.xbm")
    maskfile = fixture_path(r"xbm_cursors/white_sizing_mask.xbm")
    cursor = pygame.cursors.load_xbm(cursorfile, maskfile)
    
    with open(cursorfile) as cursor_f, open(maskfile) as mask_f:
      cursor = pygame.cursor.load_xbm(cursor_f, mask_f)
      
    pygame.display.init()
    try:
      pygame.mouse.set_cursor(*cursor)
    except pygame.error as e:
      if 'not currently supported' in str(e):
        unittest.skip('skipping test as set_cursor() is not supported')
    finally:
      pygame.display.quit()
      
if __name__ == '__main__':
  unittest.main()
```

```
```

```
```

