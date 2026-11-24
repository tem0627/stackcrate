# StackCrate — 箱の使い方 / Player guide

## 日本語

### 空箱を作る

標準レシピは作業台の3×3です。サーバー独自のレシピに変更されている場合は、その設定に従ってください。箱は結果欄から手動で1個ずつ作ります。

| 左 | 中央 | 右 |
| --- | --- | --- |
| ネザライトインゴット | ネザースター | ネザライトインゴット |
| シュルカーの殻 | エンダーチェスト | シュルカーの殻 |
| シュルカーの殻 | 空のバンドル | シュルカーの殻 |

### 収納・取り出し・建築

| やりたいこと | Java版の操作 |
| --- | --- |
| 素材を登録・収納する | 自分のインベントリで、丸石などの素材と箱を重ねて左または右クリック。空箱には最初に入れた素材が登録され、以降はその素材だけ入ります。 |
| 自動で拾う | 中身入りの箱をホットバーか通常インベントリに入れて、登録済みの素材を拾います。サーバー側で自動回収が有効な場合のみ。空箱へ勝手に素材は登録されません。 |
| 1スタック分を出す | 箱をカーソルで持ち、自分のインベントリの空き枠を右クリック。画面を開かず出したいときは、箱を主手に持って、スニークしながらブロックへの攻撃操作をします。 |
| 一括で出し入れする | 自分の持ち物画面で箱をダブルクリック。通常は同種の素材があれば容量まで収納し、なければ空き枠に入る分を取り出します。収納対象がある状態で箱が満杯なら、通常の取り出し操作を使ってください。 |
| 箱からブロックを置く | 中身入りの箱を手に持ち、ブロックを通常どおり設置します。設置が成立したときだけ、その素材を1個消費します。一部の素材は先に取り出す必要があります。 |

取り出す場所に空きがなければ、入らない分は箱に残り、足元には落ちません。使い切ると箱は未登録の状態に戻り、別の素材を登録できます。外観パックなしでは、空箱はチェスト、中身入りは素材の見た目になります。

### 残りを捨てて空箱に戻す

この機能が有効なサーバーでは、2×2または3×3の製作枠のどこかに、**中身入りの箱だけを1個**置きます。結果欄で素材と数量を確認できます。箱を入力欄から取り戻したり画面を閉じたりすれば中身は残りますが、**結果を取ると中身が永久に破棄されます**。取り出したいだけなら、上の取り出し操作を使ってください。

名前付きや独自データ付きのアイテムは収納対象外です。箱を別のバックパックなどに移す場合は、先にテスト用の箱で保存・復元を確認してください。

## English

- **Get a box:** use the crafting table and the default 3×3 recipe shown above (netherite ingots, nether star, shulker shells, ender chest, empty bundle), or follow your server's configured recipe. Take the result manually, one at a time.
- **Store:** overlap a normal material and the box in your inventory. The first material sets the type. An assigned box in the hotbar or main inventory can automatically collect matching pickups if enabled.
- **Withdraw:** hold the box on the cursor and right-click an empty inventory slot. Alternatively, hold it in your main hand, crouch, and attack a block for up to one stack. Items that do not fit stay in the box.
- **Bulk transfer:** double-click the box in your own player inventory. If matching loose items are present, the normal behavior is to deposit up to capacity; otherwise it withdraws into empty slots. Use the regular withdrawal gesture if the box is full and matching items are present.
- **Build:** with the filled box in hand, place the stored block as usual. Successful placement uses one stored item. Some materials must be withdrawn before placement.
- **Reset:** if enabled, put one filled box alone in any slot of a 2×2 or 3×3 crafting grid. Inspect the result preview: **taking the result permanently discards the contents**. Closing the screen without taking the result does not.

Emptying the box allows a different material to be registered. Named or custom items are not accepted. Test third-party backpacks with disposable items before storing valuable boxes.
