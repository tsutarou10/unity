## 1. タイトル画面の作り方
	1. タイトル画面の次に遷移したいSceneの名前をstage01とする (後で紹介するスクリプトに合わせるため)
	2. Project -> Create -> Scene -> Rename -> Titleと入力
	3. 好きにデザインを作る (以下例)
		1. MainCameraのInspector -> ClearFlagsをSolidColorにする
		2. HierarchyのUI -> Textを選択
		3. 自由にText、Font Sizeを変更
		4. HierarchyのUI -> Buttonを選択
		5. Buttonのテキストや位置を自由に変更
		6. C#スクリプトを書く
		7. SceneButton.csをButtonオブジェクトに取り付ける
		8. ButtonのInspector -> OnClickの◎の横のスペースにからButtonオブジェクトをドラッグ
		9. No FunctionとなっているところをSceneButton -> SceneLoadStage01()に変更
		10. File -> Build Settings -> Add Open Scenesで現在のSceneを使えるようにする
		11. Titleでゲームスタートした後にボタンをクリックすると画面が遷移する
	4. 画面遷移した後Sceneが暗くなった時の対処法
		1. Window -> Lighting -> Settings
		2. Sceneタブを選択 -> Auto Generateのチェックを外す -> Generate Lightingをクリック

![実行例](https://github.com/tsutarou10/unity/blob/master/gif/SceneTitle.gif)

```:SceneButton.cs
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;

public class SceneButton : MonoBehaviour {
	public void SceneLoadStage01() {
		SceneManager.LoadScene("stage01");
	}

	public void SceneLoadTitle() {
		SceneManager.LoadScene("Title");
	}
}
```
## 2. フィールドの作り方

## 3. プレイヤーの作成と移動

## 4. カメラの位置設定 (プレイヤーを追従)

## 5. 敵キャラの作成 (プレイヤーを追従)
	1. 検知エリア (ある距離内に入ったら追従するようにする)
	1. 敵キャラに衝突したらゲームオーバー
	1. ランダムで複数生成

## 6. アイテムを拾う
	1. アイテムの個数を画面表示

## 7. アイテムを置く
	1. 爆弾を綺麗に配置できるようにする必要がある
	1. アイテム自動削除
		1. 周囲にあるブロック破壊 (火を出して火と衝突したブロックを削除?)

## 8. エフェクト
	1. 爆発
	1. 連鎖
	1. ブロックの破壊
	1. プレイヤーの死

1. ゲームクリア画面、ゲームオーバ画面の作成


## Inputについて
```C#
if(Input.GetKey(KeyCode.Space)) {
	// スペースキーが押された時の処理
}
```
| 名前 | 内容 |
| :---: | :---: |
| KeyCode.Space | スペース |
| KeyCode.Return | リターンキー |
| KeyCode.UpArrow | 上向き矢印 |
| KeyCode.DownArrow | 下向き矢印 |
| KeyCode.RightArrow | 右向き矢印 |
| KeyCode.LeftArrow | 左向き矢印 |
| KeyCode.A | a |
| KeyCode.LeftControl| 左側のコントロールキー |
| Input.GetKey | キーを押してる間は常に有効 (連射など) |
| Input.GetKeyDown | キーを押していない状態から押した時 |
| InputGetKeyUp | キーを押している状態から離した時 |

## レイヤーって何？
## RayCastとは
