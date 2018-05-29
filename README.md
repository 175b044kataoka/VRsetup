# VRの色々
- UnityでHIT Viveのセットアップ
- 照準カーソルの設定

***
## UnityでHIT Viveのセットアップ
※前提として外部機器の設置が終わっている事とする
1. メニューの[Edit] → [Project Settings] → [Player]と選択
1. [Inspector]の一番下の[XR Settings]を開く
1. [Virtual Reality SDKs]の[+]を押すと[Oculus]と追加される
1. Steamアカウントを作成 or Steamアカウントにログインする  
1. Sceneをplayする
これでVR視点になる

***
## 照準カーソルの設定
視点に合わせて動くポインタの様な物を設定する時のあれこれ  
- Canvasの設定
    - Render ModeをWorld Spaceに設定(Render Modeの詳細は[こちら](http://tech.pjin.jp/blog/2017/03/02/unity_ugui_canvas_rendermode/ "TECH pjin 【Unity】uGUIのCanvasとRenderModeについて"))  
    - Scaleをx.y.zを全て0.00135,Width/Heightを640.480,Dynamic Pixel Per Unitを10に設定(DefaultとしてPrefab化しておくとよい)
- カメラの設定
    - Main Camera/UICameraとして二つ用意
    - 空のゲームオブジェクトを作り、二つとも子にしておく
    - CameraのCulling Maskの項目をmainCameraはUi以外に、UICameraはUIにだけチェックを付けておく
    - UICameraのClear FlagsをDepth Onlyに設定
- カーソルの作成
    - default CanvasをUICameraの子にする
    - Canvasを選択したまま[Create] → [UI] → [Raw Image]と選択
    - RawImageをカーソルの様に丁度よく設定
    
※注意点:視界に合わせて動かないUIを設定したい時はUIカメラを無効化する
    
***
