🚜 AGX Excavator Simulation (AGX_Test)

AGX Dynamics を用いた油圧ショベルの掘削シミュレーション。
AGX SDK の agxviewer 環境で動作し、粒子（砂）を掬う動作とパラメータ調整が可能です。

🔧 実行手順
必要環境

AGX Dynamics 2.40+

有効なライセンス

Visual Studio Build Tools 17+

Windows環境推奨

実行方法

AGX Dynamics Command を開く

以下のコマンドを実行：

agxviewer AGX_Test/test3.agxPy


※ ダブルクリックでは UI が出ません。必ず AGX Command から起動してください。

🧩 シミュレーション概要
ファイル	機能概要
test1.agxPy	初期デモ。ショベルモデル＋粒子生成。動作確認用。
test2.agxPy	Lock1Dと関節制御の安定化、粒子接触パラメータ修正。
test3.agxPy	🎮 UI・スコアリング機能を追加。掘削効率をリアルタイム測定。
🕹 操作方法
キー	機能
E	掘削開始（ベースライン保存＋スコア測定開始）
R	ショベル・リンク機構をリセット
Shift + R	粒子ベッドを再配置・再起動
A	Apply モード切替
L	Toggle モード切替
[ / ]	Friction（摩擦）調整
{ / }	Damping（減衰）調整
, / .	Adhesion（付着）調整
- / =	Force（油圧出力）調整
📊 スコアリング仕様

HUD上に表示：

指標	意味
Moved	判定を満たした粒子の数
Mass	現在持ち上げている粒子の合計質量（lift）
MaxH	最も高い粒の高さ（z）
Time	掘削開始からの経過秒数

基準：

移動距離閾値：0.15 m

高さ上昇閾値：0.35 m

設定：SCORE_CONFIG 内で調整可能

⚙️ チューニングガイド

Shift+R で粒子を整地

E で掘削開始

Friction / Adhesion / Force を微調整しながら HUD を確認

Lift（Mass）と Peak が増える設定を探す

スコアが0ならしきい値を下げる

🪄 今後の開発予定

UIから SCORE_CONFIG と ContactMaterial を操作可能に

Lift/Peak のログを CSV 出力

掘削効率（質量/時間）KPI追加

Unreal Engine プラグイン連携テスト

👤 Author

Tango Saito (齋藤旦伍)
Waseda University – Silvereye Project
AGX Excavator Simulation Research

📎 実行例

🧰 ライセンス

本プロジェクトは AGX Dynamics Evaluation License の範囲内で実行されています。

🧩 GitHub コマンド

README を保存したら、以下で push！

git add README.md
git commit -m "Update README with test3.agxPy details"
git push origin main
