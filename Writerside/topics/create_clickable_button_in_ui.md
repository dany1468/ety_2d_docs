# [WIP] UI にクリックできるボタンを作る

## いつ何をするのか？ 

これは、「Group 6: タッチするとシーンを切り替える (`OnMouseDown_SwitchScene`)」を UI に応用したものです。

`OnMouseDown_SwitchScene` は、シーン内の画像ボタンをクリックしていますが、ここではより Unity らしく、UI で作成したボタンに同様の機能を付けます。

## スクリプト

```C#
using UnityEngine;
using UnityEngine.SceneManagement;

public class UI_SwitchScene : MonoBehaviour
{
    public string sceneName; // シーン名：Inspectorで指定
    
    public void SwitchScene() => SceneManager.LoadScene(sceneName);    
}
```

`OnMouseDown_SwitchScene` では `OnMouseDown` という Unity のイベントを使っていましたが、ここではどんなメソッド名でも問題ありません。今回は仮に `SwitchScene` としています。

