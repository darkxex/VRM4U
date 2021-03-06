# VRM4U

[English Doc](https://github.com/ruyo/VRM4U/blob/master/README_en.md)

## はじめに
VRM4U はVRMファイルのインポーター兼ランタイムローダーです

詳細はこちらから
https://github.com/ruyo/VRM4U/wiki/VRM4U

## 特徴
|||
|----|----|
|![2](https://github.com/ruyo/VRM4U/wiki/images/shot/03.png)|![2](https://github.com/ruyo/VRM4U/wiki/images/shot/04.png)|
|![2](https://github.com/ruyo/VRM4U/wiki/images/shot/01.png)|![2](https://github.com/ruyo/VRM4U/wiki/images/shot/02.png)|

 - VRMファイルをインポートできます。
 - アニメーション
     - 骨、Morphtarget・BlendShapeGroup、揺れ骨・コリジョン などが生成されます。
     - 揺れ骨の挙動はVRMSpringBoneかPhysicsAssetを選択できます。
     - Humanoid用のRIGが生成されるので、アニメーションを手軽にリターゲット可能です。
 - マテリアル
     - MToonを再現したマテリアル。影色の指定や、アウトラインの色・太さ調整、MatCapなど一通り適用されます。
     - 既存のPBR背景の中にキャラクタを描画できます。ポストプロセスを利用しません。
     - モバイルでも描画可能です。(Forward/Deferred両対応) 

## 動作環境
 - UE4.20、UE4.21、UE4.22
 - UE4.19も動きますが、マテリアルは生成されません。

## 使い方
- [releases](https://github.com/ruyo/VRM4U/releases/latest)より利用するバージョンのプラグインをダウンロードし、
   「.uproject」とおなじ場所に「Plugins」フォルダを展開してください。

### サンプルマップ
- VRM4UContent/Maps/VRM4U_sample.umap
- ContentBrowserに表示されない場合は、以下の項目を確認ください。
![3](https://raw.githubusercontent.com/wiki/ruyo/VRM4U/images/samplemap.png)

### 使い方
- VRMファイルをドラッグ＆ドロップしてください

![2](https://github.com/ruyo/VRM4U/wiki/images/overview.gif)

## 作った人
[@ruyo_h](https://twitter.com/ruyo_h)

## ライセンス
MIT(VRM4U)

3-clause BSD-License(assimp)

### ソース
UE4アカウントの紐づけが必要です。  
https://github.com/ruyo/UnrealEngine_VRM4UPlugin

https://github.com/ruyo/assimp

公開の体裁を含め 多くの方の情報を参考にさせて頂いています。  
ありがとうございます。

### リリース履歴
- 2019/04/21 MorphTargetのY座標が正負反転していたのを修正した。
- 2019/04/18 モデル法線を正規化するようにした。モバイルでのマテリアルのエラーを修正した。
- 2019/04/08 大幅に整頓
    - デフォルトマテリアルをUnlitにした
    - 輪郭線描画をアタッチタイプに統一した。サンプルを置き換えた。
    - 動作が安定したのでAsset強制保存をの機能を外した。
- 2019/04/04 アタッチで輪郭線描画できるActorを追加した。
- 2019/03/31 UE4.21のマテリアル編集時に停止するため、パッチ対処した。
    - 停止の仮対処としてAssetを強制保存するようにした。
    - VRMファイルによっては停止することがあったのを、AssImp側で修正した。
- 2019/03/28 マテリアル最適化時、メモリアクセス違反が起きるのを修正した。
    - VRMSpringBoneがPhysicsCollisionに反応するようにした。
    - リターゲットのプレビューにモデルが表示されないのを修正した。（BoundingBoxをセットした）
- 2019/03/24 サンプルマップを追加した。
- 2019/03/23 VRMSpringBoneを仮実装した。輪郭線の描画方法を変更した。
- 2019/03/05 MotionController,LeapMotionによるトラッキングのAnimBPを追加した
- これ以前のものはこちら → https://github.com/ruyo/VRM4U/blob/master/CHANGELOG.md

