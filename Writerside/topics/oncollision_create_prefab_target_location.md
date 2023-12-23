# 衝突すると、指定の場所にプレハブを作る

## いつ何をするのか？ 

これは、「Group 7: プレハブ」の「衝突すると、そこにプレハブを作る (`OnCollision_CreatePrefab`)」の応用です。

![](oncollision_create_prefab_target_location.png)

## スクリプト

`OnCollistion_CreatePrefab` は、衝突した箇所にプレハブを作るため、 `OnCollisionEnter2D` イベントでプレハブを作成していましたが、このスクリプトでは `OnTriggerEnter2D` でも動作するようにしています。

```C#
using UnityEngine;

// 衝突すると、指定の場所にプレハブを作る
public class OnCollision_CreatePrefab_Location : MonoBehaviour
{
    public string targetObjectName; // 目標オブジェクト名：Inspectorで指定
    public GameObject newPrefab; // 作るプレハブ：Inspectorで指定
    public GameObject targetLocationObject; // プレハブを作る指定の場所：Inspectorで指定

    private void OnTriggerEnter2D(Collider2D collision)
    {
        // もし、トリガーしたものの名前が目標オブジェクトだったら
        if (collision.gameObject.name == targetObjectName)
        {
            CreatePrefabAtTargetLocation();
        }
    }

    private void OnCollisionEnter2D(Collision2D collision)
    {
        // もし、衝突したものの名前が目標オブジェクトだったら
        if (collision.gameObject.name == targetObjectName)
        {
            CreatePrefabAtTargetLocation();
        }
    }

    private void CreatePrefabAtTargetLocation()
    {
        // 衝突位置にプレハブを作る
        var newGameObject = Instantiate(newPrefab) as GameObject;
        // 指定の場所の position を取得
        var pos = targetLocationObject.transform.position;
        
        pos.z = -5; // 手前に表示
        newGameObject.transform.position = pos;
    }
}
```

ここでは、プレハブの出現場所は指定の場所であるため、 `targetLocationObject.transform.position` で直接指定しています。

`targetLocationObject` は下の図のようにインスペクターから指定しますが、シーン内のオブジェクトとしては `EmptyObject` (空のオブジェクト) で十分です。

![](oncollision_create_prefab_target_location_2.png)

## レベルアップ 🆙

作るプレハブが、もしトラップや、プレイヤーを攻撃する飛び道具であれば、「時間切れになると、自分自身を削除する (`OnTimeout_DestroyMe`)」や「画面の外に出ると、自分自身を削除する (`OnOutsideScene_DestroyMe`)」 を付けておくと、きれいに削除できるはずです。  
作りっぱなしにならないように注意しましょう。
