# sample_sm_flexbe

7.3節のサンプルプログラム  
FlexBEによる二状態のステートマシンのプログラム


## 実行

1. `FlexBE WebUI`を実行します．
  ```console
  $ ros2 launch flexbe_webui flexbe_full.launch.py
  ```

> [!NOTE]
> `FlexBe WebUI`が起動されない場合は，依存関係のインストールされていない可能性があります．
その際，`flexbe_webui`のフォルダーの中で，`pip3 install -r requires.txt`を実行してください．

2. `Behavior Dashboard`が表示されます．
![](../docs/sample_sm_flexbe/01_behavior_dashboard.png)

3. `Load Behavior`を押し，右側にBehavior一覧が表示されます．
![](../docs/sample_sm_flexbe/02_load_behavior.png)

4. その中から，`Sample Behavior`というBehaviorを選択します．
![](../docs/sample_sm_flexbe/03_loaded_behavior.png)

5. `Statemachine Editor`に移動して，ステートマシンの状態を確認します．
![](../docs/sample_sm_flexbe/04_statemachine_editor.png)

6. `Runtime Control`に移動して，ステートマシンを実行します．
そのために，まず`max_eat`という値を設定します．

> [!NOTE]
> `max_eat`はユーザーが食べられるスイーツの数のことを表します．その値を自由に変えられます．

![](../docs/sample_sm_flexbe/05_runtime_control.png)

7. 次に，`Start Execution`を押して，状態が開始されます．

| Searchステート | Eatステート |
| --- | --- |
| ![](../docs/sample_sm_flexbe/06_search.png) | ![](../docs/sample_sm_flexbe/07_eat.png) |

8. 実行ターミナルの結果の一例．
  ```console
  [00:50:45] Onboard engine is ready.
  [00:50:50] --> Mirror - received updated structure with checksum id = 551566305
  [00:50:50] Activate mirror for behavior id = 551566305 ...
  [00:50:50] --> Preparing new behavior...
  [00:50:50] Executing mirror ...
  [00:50:50] Onboard Behavior Engine starting [Sample Behavior : 551566305]
  [00:50:52] スイーツを探索しています
  [00:50:52] スイーツを見つけました！
  [00:50:53] スイーツを1個食べます！
  [00:50:53] 現時点では、スイーツを1個食べました！
  [00:50:54] スイーツを探索しています
  [00:50:54] スイーツを見つけました！
  [00:50:55] スイーツを1個食べます！
  [00:50:55] 現時点では、スイーツを2個食べました！
  [00:50:56] スイーツを探索しています
  [00:50:56] スイーツを見つけました！
  [00:50:57] スイーツを1個食べます！
  [00:50:57] 現時点では、スイーツを3個食べました！
  [00:50:58] スイーツを探索しています
  [00:50:58] スイーツを見つけました！
  [00:50:59] スイーツを1個食べます！
  [00:50:59] 現時点では、スイーツを4個食べました！
  [00:51:00] スイーツを探索しています
  [00:51:00] スイーツを見つけました！
  [00:51:01] スイーツを1個食べます！
  [00:51:01] 現時点では、スイーツを5個食べました！
  [00:51:02] スイーツを探索しています
  [00:51:02] もうお腹いっぱいです・・・
  [00:51:02] PreemptableStateMachine 'Sample Behavior' spin() - done with outcome=finished
  [00:51:02] No behavior active.
  [00:51:02] [92m--- Behavior Mirror ready! ---[0m
  ```


## Statesの一覧

* [search_state.py](sample_sm_flexbe_states/sample_sm_flexbe_states/search_state.py):
  * スナックを探す状態の実装

* [eat_state.py](sample_sm_flexbe_states/sample_sm_flexbe_states/eat_state.py):
  * 見つけたスナックを食べる状態の実装

* [grasp_state.py](sample_sm_flexbe_states/sample_sm_flexbe_states/grasp_state.py):
  * 見つけたスナックを把持する状態の実装（発展版）


## Behaviorsの一覧

* [sample_behavior_sm.py](sample_sm_flexbe_behaviors/sample_sm_flexbe_behaviors/sample_behavior_sm.py):
  * 食べ物の探索と食事の状態を含めたSampleタスクのためのステートマシン


## ヘルプ

## 著者

萩原 良信


## 履歴


## ライセンス

Copyright (c) 2025, HAGIWARA Yoshinobu, VALENTIN CARDENAS Keith and OKUMA Yuki.  
All rights reserved.  
This project is licensed under the Apache License 2.0 license found in the LICENSE file in the root directory of this project.

## 参考文献

