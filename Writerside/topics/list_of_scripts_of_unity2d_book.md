# Unity2D超入門講座 スクリプト一覧表

これは、書籍「楽しく学ぶ Unity 2D 超入門講座」の巻末に収録されている、スクリプト一覧表です。

| Group 1: ずっと  |                  |
|---------------|------------------|
| ずっと、移動する (水平) | `Forever_MoveH`  |
| ずっと、移動する (垂直) | `Forever_MoveV`  |
| ずっと、回転する      | `Forever_Rotate` |
| ときどき、曲がる      | `Sometime_Turn`  |
| ときどき、反転する     | `Sometime_Flip`  |

| Group 2: 移動       |                         |
|-------------------|-------------------------|
| キーを押すと、スプライトが移動する | `OnKeyPress_MoveSprite` |

| Group 7: プレハブ         |                               |
|-----------------------|-------------------------------|
| タッチすると、そこにプレハブを作る     | `OnMouseDown_CreatePrefab`    |
| ときどき、範囲内にランダムにプレハブを作る | `Sometime_RandomCreatePrefab` |
| キーを押すと、近くにプレハブを作る*    | `OnKeyPress_CreatePrefab`     |
| 衝突すると、そこにプレハブを作る*     | `OnCollision_CreatePrefab`    |
| 時間切れになると、自分自身を削除する    | `OnTimeout_DestroyMe`         |
| 画面の外に出ると、自分自身を削除する*   | `OnOutsideScene_DestroyMe`    |
| 衝突すると、自分自身と相手を削除する*   | `OnCollision_Destroy`         |
| 衝突すると、自分自身を削除する*      | `OnCollision_DestroyMe`       |
