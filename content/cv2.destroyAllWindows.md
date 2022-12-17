---
title:
 'cv2.destroyAllWindows'
---

mac/linux環境だと効かないことが多い
ネット上のやつとかみてもうまくいくのと行かないのがある
playground.py

```
cv2.imshow("img",img)

cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.waitKey(0)
```

で解決した

- 環境: mac / pycharm / python 3.7
