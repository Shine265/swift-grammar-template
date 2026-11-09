# 日専祭アプリ：天星

> **チーム：** チーム名:Nerv, 氏名:26CMシャィン　コ　コ　アウン
> メンバー名:26CM0106カウン ミャット トゥー、26CM0127ハン トゥン ゾー
> **AI利用レベル：** 2（生成コード可）
> **最終更新：** 2026-10-05

> 💡 制作の進め方は担任の先生から案内があります。このファイルの項目は、担任の先生の指示で増えることがあります。

---

## 何ができるアプリか（3行）

>このアプリは、星について詳しく知ることができるアプリです。

>星の名前や特徴、明るさなどの情報を分かりやすく紹介します。

>また、星の画像を見ることもでき、楽しみながら星について学ぶことができます。

## 画面
#アプリの画像

<img width="300"  alt="screen1" src="https://github.com/user-attachments/assets/e78c9d64-f910-40bb-b9aa-4dc4b1ebda3e" />



## 使った文法・技術

#Swift の文法
構造体(struct): SkyStar、Constellation、ZodiacSign などのデータと画面
列挙型(enum): AppLanguage(en / ja / my)
クラス(class): JourneyStore、Camera、SkyMusic
拡張(extension): Color(hex:) で16進数の色を使えるようにした
配列: append(occupiedLabels.append、order.append)と remove(at:)(orderedStars.remove(at:))
集合(Set): お気に入りの保存。insert と remove で追加・削除
辞書(Dictionary): 星座の線のデータ(figures)や多言語の文章(strings)
オプショナル: ?、??、if let、guard let
switch 文: 誕生日から星座を判定(case 321...419:)
クロージャ: map、filter、first(where:)、contains(where:)
async / await: 音楽のフェードアウト後に一時停止する処理

#SwiftUI の部品
List: 星座と星の一覧(Browse 画面)
ForEach: 星座カード、検索結果、星の名前ボタンなど
LazyVGrid: 星座カードのグリッド表示
TabView: 4つのタブ(旅 / 星空 / 星座 / 発見)
NavigationStack / NavigationLink: 詳細画面への移動
.sheet: 設定、誕生日、星の詳細
TextField: 検索バー
Picker: 言語、12星座 / 13星座、すべて / 保存済み
Toggle / Slider: 星空の設定と BGM の音量
DatePicker: 誕生日の選択
Canvas: 星空マップ、銀河、星座の絵の描画
TimelineView: 星空のアニメーション

#状態管理
@State: 検索文字、シートの開閉、選択中の星
@Binding: 選択中の星を SkyMapView と共有
@StateObject / @EnvironmentObject: アプリ全体で共有する JourneyStore
@Published: タブやお気に入りの変更を画面に反映
@AppStorage: 言語、誕生日、音量、設定の保存
UserDefaults: ブックマーク(お気に入り)の保存

#操作・アニメーション
DragGesture: ドラッグで星空を動かす(慣性つき)
MagnificationGesture: ピンチで拡大・縮小
SpatialTapGesture: 星をタップして選ぶ
withAnimation: 画面の切り替えや光の動き
ViewModifier / ButtonStyle: 独自のアニメーションとボタンの動き(.appear、.shimmer)

#データ・その他
JSON と Decodable: stars.json などの読み込み
AVAudioPlayer: 星空画面の BGM(ループ再生とフェード)
触覚フィードバック(Haptics): タップ時の振動
多言語対応: 日本語、英語、ビルマ語
アクセシビリティ: VoiceOver 用ラベル、「視差効果を減らす」設定への対応
数学: sin / cos(銀河の渦巻き)、座標変換(星空マップの project())

## 生成AIの使い方（どの場面で、どう使ったか）
アプリの80割はAIを使いました。星の情報、神話、星空を作り方法、色々なことをAIを聞いて作りました。BGMまでAIに任せました。

## 展示で工夫した点
アプリのナビゲーションはもっとシンプルにした方がいいかな。時間がなくてアプリはまだ完璧ではないです。色々入れたいこともあります。
