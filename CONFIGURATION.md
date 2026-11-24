# StackCrate — 設定と権限 / Admin guide

## 設定ファイル

初回起動で `plugins/StackCrate/config.yml` が生成されます。編集した設定は**通常再起動**で反映します。

| 項目 | 初期値 | 動作 |
| --- | --- | --- |
| `crafting.enabled` | `true` | 作業台で新しい箱を作れるか。無効でも、既存箱の利用や管理コマンドによる配布は可能。 |
| `crafting.shape` / `crafting.ingredients` | [標準3×3レシピ](USAGE.md) | レシピの配置と材料。変更するときは2項目を一緒に指定。 |
| `storage.max-items-per-box` | `9223372036854775807` | 箱1個に追加収納できる上限。引用符なしの正の整数で指定。 |
| `storage.excluded-materials` | `[]` | 新しく収納・自動回収できない素材の一覧。 |
| `auto-pickup.enabled` | `true` | 登録済みの箱への自動回収を有効にするか。 |
| `reset.enabled` | `true` | 製作枠から中身を永久破棄するリセットを使えるか。 |
| `display.glint` | `true` | 中身入りの箱の光沢。他の外観パックは変更しません。 |

例：銅・エンダーパール・樽で作り、1箱4,096個まで。ダイヤモンドとネザライトブロックの追加収納を除外し、破棄リセットを無効にする場合：

```yaml
crafting:
  enabled: true
  shape: ["CRC", "CBC", "CCC"]
  ingredients:
    C: minecraft:copper_ingot
    R: minecraft:ender_pearl
    B: minecraft:barrel
storage:
  max-items-per-box: 4096
  excluded-materials: [minecraft:diamond, minecraft:netherite_block]
reset:
  enabled: false
```

一つの設定ファイルに、同じ見出し（`crafting:` など）を重複して追加しないでください。レシピは1～3行、1～3列で、全行の文字数を揃えます。大文字1文字を材料に割り当て、空白は空き枠です。上限を下げたり素材を除外したりしても、すでに入っているアイテムは消えず、取り出せます。不正な設定でセーフモードに入った場合も、既存箱の取り出しは可能です。サーバーログを確認して設定を修正し、再起動してください。

## 権限と管理コマンド

管理用の権限は **`stackcrate.admin`** の1つです。初期状態ではOPが持ち、権限管理プラグインでこのノードを特定の役割へ付与することもできます。**通常のクラフト、収納、取り出し、自動回収、設置には専用の権限は不要**です。操作ごとの権限はこのベータにはありません。

| コマンド | できること |
| --- | --- |
| `/stackcrate give` | ゲーム内の実行者に空箱を1個渡します。空き枠が必要。 |
| `/stackcrate give <プレイヤー名>` | オンラインのプレイヤーに空箱を1個渡します。コンソールからは対象名が必須。 |
| `/stackcrate inspect` | 実行者が主手に持った箱の素材と数量を表示します。ゲーム内のみ。 |

## English

The first start creates `plugins/StackCrate/config.yml`. Start with a fresh configuration. Restart the server normally after changes.

- **Crafting:** `crafting.enabled` controls new-box crafting (default: enabled). To customize it, set `crafting.shape` and `crafting.ingredients` together as shown above. Use one to three rows of equal width, one to three characters each, single uppercase ingredient symbols, and spaces for empty positions.
- **Storage:** `storage.max-items-per-box` is a positive integer (default: `9223372036854775807`). `storage.excluded-materials` defaults to an empty list. Both affect new deposits only; existing contents stay withdrawable.
- **Toggles:** `auto-pickup.enabled`, `reset.enabled`, and `display.glint` all default to `true`. Disable reset if players should not be able to destroy contents through crafting.
- **Safe mode:** if the plugin starts in safe mode after a config error, withdrawals still work. Check the console, fix the configuration, and restart.
- **Permissions:** `stackcrate.admin` defaults to operators and controls both admin commands. In-game, `/stackcrate give` gives yourself a box; `/stackcrate give <player>` gives one to an online player with an empty slot. The console must name the recipient. In-game `/stackcrate inspect` reports the material and count of the box in your main hand. Normal player actions do not require this permission, and the beta has no separate per-action permission nodes.
