# 🤖 SPIKEテンプレート集

## ひながた
必要なモジュールや、自分が分かりやすい変数のまとめ
``` python title="最初の呪文.py"
import runloop
import motor
from hub import port
from hub import light_matrix
from time import sleep_ms as sleep
import motor_pair
import color_sensor
import color
from hub import sound

motor_pair.pair(motor_pair.PAIR_1, port.A, port.B)
WHEEL = motor_pair.PAIR_1 #タイヤ
NAKAHARA = port.C
IMAI = port.E
MV_DG = motor.run_for_degrees #角度を指定して進むやつ
MV_P_DG = motor_pair.move_for_degrees #角度を指定して進むやつのペア
SLEEP = runloop.sleep_ms
```

## ライントレース
``` python title="ライントレース.py"
import ~
comming soon
```