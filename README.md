# Pacman

## 実行環境の必要条件
* python >= 3.10
* pygame >= 2.1

## ゲームの概要
* pygameでPacmanを作る

## ゲームの遊び方
* 

## ゲームの実装
### マップの描画
* 主人公キャラクターが移動できるマップを描画する
* イニシャライザにて生成するマップを作成する
* 1 = 壁, 0 = 道
* draw_mapにてマップの描画を行う
* is_movableにて壁との当たり判定を行う

### 主人公キャラクターの描画
* 

### 敵の描画 担当: 森山悠太
**`Enemy`クラス:**
- 敵キャラクターの管理。
- 追跡、縄張り、弱体化モード。
- **各敵の行動パターン:**
    - **Enemy ID 1:** プレイヤーを追跡。
    - **Enemy ID 2:** プレイヤーの数ステップ先を予測して追跡。
    - **Enemy ID 3:** 他の敵とプレイヤーの位置関係を見て挟み撃ち。
    - **Enemy ID 4:** 近いとランダム移動、遠いと追跡。
- `update`で行動決定、移動、モード切替。
- `find_path`でA\*アルゴリズムによる経路探索。
- `move`で経路移動。
- `make_weak`で弱体化モードへ移行。
- `get_eaten`で食べられた状態へ移行。
- `revive`で復活処理。

### アイテムの設定 担当：𠮷岡
### class Item
#### 概要
Itemクラスは、ゲーム内に配置されるコインを表示するためにクラス 。このクラスはpygame.sprite.Spriteクラスを継承しており、PygameのSprite機能を活用して、アイテムの当たり判定を効率的に行えるようにしている

#### 属性
* radius (int) : コインの半径を表す
* image (pygame.Surface) : コインの描画を使用されるSurfaceオブジェクトが描画される
* rect (pygame.Rect) : コインの位置とサイズを保持するオブジェクト

#### メソッド
- __init__ (self, x: int, y: int) :
    - Itemクラスのコンストラクタ
    - 引数としてコインが配置されるマップ上の座標を受け取る
    - コンストラクタ内で、コインの半径、描画する円、位置が設定される

### スコアの表示　担当：𠮷岡
### class Score
#### 概要
Scoreクラスは、ゲーム中のスコアを管理し、画面に表示するためのクラス。スコア値の保持、表示テキストの生成および画面への描画

#### 属性
* font (pygame.font.Font) : スコア表示に使用するフォントオブジェクト
* color (tuple) : スコア表示テキストの色を表すRGBタプル
* value (int) : 現在のスコア値を保持
* image = (pygame.Surface) : スコア値を描画したSurfaceオブジェクト
* rect (pygame.Rect) : スコア表示テキストの位置とサイズを保持するRectオブジェクト

#### メソッド 
- __init__ (self) :
    - Scoreクラスのコンストラクタ
    - コンストラクタ内で、フォント、色、初期スコア値、初期スコア表示テキスト、位置を設定
- update(self, screen : pygame.Surface) : 
    - スコア値を更新し、更新されたスコアテキストを画面に描画
    - screen引数は、スコアを表示するpygameのSurfaceオブジェクト
### スタート画面の描画
* PacmanGameのスタート画面を描画する
* スペースキーでゲームを開始

### DebugInfo クラス 担当: 森山悠太
- プレイヤー情報の表示
- 敵の情報の表示と経路の描画
- アイテム情報の表示


### ToDo
- 
- 

### メモ
* 
