## 命令一覧

stamp Unicode ASCII はぞれぞれ等価な命令です。
| stamp | Unicode | ASCII | 意味 |
| ---------------------------------------------------------------------------------------- | ----------- | ------------------- | ------------------------------------------------------------------------------------------- |
| :arrow_forward: | ▶️ | `>` | 使うスタックを一つ右に移動する |
| :arrow_backward: | ◀️ | `<` | 使うスタックを一つ左に移動する |
| :arrow_down_small: | 🔽 | `v` | 使うスタックを一つ下に移動する |
| :arrow_up_small: | 🔼 | `^` | 使うスタックを一つ上に移動する |
| :arrow_heading_up: | ⤴ | `i` | スタックからポップし、その値を+1 してプッシュする |
| :arrow_heading_down: | ⤵ | `d` | スタックからポップし、その値を-1 してプッシュする |
| :pushpin: | 📋 | `.` | ポップし、出力して、プッシュする |
| :blob_pyon_inverse: | 🗼 | `[` | ポインタが指す値が 0 なら、対応する `]`の直後にジャンプする。 |
| :blob_pyon: | 🎓 | `]` | ポインタが指す値が 0 でないなら、対応する `[`の直後にジャンプする。 |
| :point_right: | 🍰 | `(` | 右向きに回転する 向=足 × 向 |
| :point_left: | 🦌 | ｀)`               | 左向きに回転する 向=向 × 足                                                                 |
| :point_up_2:                                                                             | 🦑          |`A`                | 上を向くように回転する 足=向, 向=-足                                                        |
| :point_down:                                                                             | 🦪          |`V`                | 下を向くように回転する 足=-向, 向=足                                                        |
| :leftwards_arrow_with_hook:                                                              | 🦾          |`n`                | 時計回りに回転する 足=向 × 足                                                               |
| :arrow_right_hook:                                                                       | 🐢          |`c`                | 反時計回りに回転する 足=足 × 向                                                             |
| :zzz:                                                                                    | 💤          |`N`                | 何もしない                                                                                  |
| :stop_button:                                                                            | 🚧          |`;`                | プログラムを終了させる                                                                      |
| :inbox_tray:                                                                             | 🤥          |`\` | 次の文字をそのままスタックにプッシュする |
| :slot_machine: | 💫 🌀 | `?` | ランダムに回転する |
| :repeat: | 🔁 | `T` | ポップし、-なら左回転、0 なら回転なし、+なら右回転 |
| :arrows_clockwise: | 🔃 | `I` | ポップし、-なら下回転、0 なら回転なし、+なら上回転 |
| :arrows_counterclockwise: | 🔄 | `G` | ポップし、-なら反時計回り、0 なら回転なし、+なら時計回り |
| :cross: | ✝️ | `a` | すべてのスタックを加算関数で畳み込む |
| :negative_squared_cross_mark: | ❎ | `m` | すべてのスタックを乗算関数で畳み込む |
| :zero_score: | 🍩 | `f` | スタック内の 0 を削除する |
| :regional_indicator_y: | 🇾 | `y` | y->x, x->z, z->y となるようにスタックの向きを変える。何もない部分は詰められる |
| :regional_indicator_z: | 🇿 | `z` | y の変換方向が逆のバージョン |
| :heavy_plus_sign::heavy_minus_sign::heavy_division_sign::heavy_multiplication_x::modulo: | ➕➖✖️➗ ㌫ | `+` `-` `*` `/` `%` | b,a をポップし、演算 a `+` `-` `*` `/` `%` b の結果をプッシュ |
| :scales: | ⚖️ | `` ` `` | y,x をポップし、x>y の時 1, x<y の時-1, y=x なら 0 をプッシュする |
| :dna: | 🧬 | `'` | ポップし、二回プッシュする |
| :fast_forward: | 🈚 | `#` | 次の文を無視する |
| :popcorn: | 🍿 | `$` | ポップし、捨てる |
| :julia_three_balls: | 🍡 | `j` | z,y,x の順にポップし、コードをその場所に移動し、移動前の場所を x,y,z の順でプッシュする |
| :four_leaf_clover: | 🍀 | `F` | d,z,y,x の順にポップし、コードをその場所に移動し、移動前の場所を x,y,z,d の順でプッシュする |

## サンプルコード

fizzbuzz

```
iii''''m     > iiiiiii'iii* > iiiiiii''+i*   > iiiii'+i'*i <<v (
v ii''''m    ^ iiii''mii    > iiiii'+i'*dddd > iiiii'+i'*i<<<^A)
N                   A             iiiii-'' '           A

N                               (^(          (v(              N
('T;                    )                         )           V#
d )vi vi^ ' ''-iii #A % T v''-^ ) )>.>.>..<<<) ) #( nn A
(^^<.>v A               )                         )
N                               ( (          ( (

N            (d^'[' ''- iii'*i % ' v''-^ [dvi^]$ - ''- iii'*i /](
N        )                           $^]i$. + dd*'iiiiiii-''[i v(
N                                                      V(
N       V(#^ T m v                                      (
```
