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
ライントレースの方法
``` python title="ライントレース.py"
import runloop
import motor_pair
from hub import port
import color_sensor

# セットアップ
motor_pair.pair(motor_pair.PAIR_1, port.A, port.B)
WHEEL = motor_pair.PAIR_1

# 設定値
BASE_SPEED = 300 # 基本の速さ
TARGET_LIGHT = 50 # 目標値（黒10%と白90%の中間など、環境に合わせて調整）
GAIN = 1.5        # 修正の強さ（大きくするとキビキビ動くが、振りすぎに注意）

async def line_trace():
    while True:
        # 反射光の強さを取得 (0-100)
        # 0が真っ黒、100が真っ白に近い
        reflection = color_sensor.reflection(port.F)
        
        # 偏差（ズレ）を計算
        error = reflection - TARGET_LIGHT
        
        # 左右の速度差（ステアリング値）を計算
        # 黒いとき（reflection小）は右へ、白いとき（reflection大）は左へ
        steering = int(error * GAIN)
        
        # モーターを動かす
        # move(pair, steering, velocity)
        motor_pair.move(WHEEL, steering, velocity=BASE_SPEED)
        
        # CPU負荷を抑えるために少し待機
        await runloop.sleep_ms(10)

async def main():
    print("Line trace start!")
    await line_trace()

runloop.run(main())
```

## 色分け
色分けの方法
``` python title="色分け.py"
import runloop
import motor_pair
# coming soon
```

ipadで編集したよ
