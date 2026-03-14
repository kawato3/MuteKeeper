---
title: "アンインストール — MuteKeeper"
description: "MuteKeeper を macOS・Windows から完全にアンインストールする方法。"
---

# アンインストール

MuteKeeper をシステムから削除する手順を OS ごとに説明します。

---

## Windows

### アプリの追加と削除から削除する（推奨）

1. **設定** > **アプリ** > **インストールされているアプリ**（Windows 10 では「アプリと機能」）を開く
2. 一覧から **MuteKeeper** を探す
3. **アンインストール** をクリックし、画面の指示に従う

これにより、インストーラーが配置したファイルがすべて自動的に削除されます。

### 手動で削除する

エクスプローラーで以下のフォルダーを削除してください。削除には管理者権限が必要です。

```
C:\Program Files\Common Files\VST3\MuteKeeper.vst3
C:\Program Files\Common Files\CLAP\MuteKeeper.clap
```

---

## macOS

macOS ではアンインストーラーは提供していません。以下のファイルを手動で削除してください。

### 1. プラグイン ファイルの削除

インストール時に選択した形式に応じて、該当するファイルを削除します。

#### VST3

```bash
sudo rm -rf "/Library/Audio/Plug-Ins/VST3/MuteKeeper.vst3"
```

#### AUv3（Standalone アプリ）

AUv3 プラグインは Standalone アプリ内に埋め込まれています。アプリを削除すると AUv3 も削除されます。

```bash
sudo rm -rf "/Applications/MuteKeeper.app"
```

#### AAX

AAX をインストールした場合は、以下も削除してください。

```bash
sudo rm -rf "/Library/Application Support/Avid/Audio/Plug-Ins/MuteKeeper.aaxplugin"
```

#### CLAP

CLAP をインストールした場合は、以下も削除してください。

```bash
sudo rm -rf "/Library/Audio/Plug-Ins/CLAP/MuteKeeper.clap"
```

!!! tip "Finder で削除する場合"
    ターミナルを使わずに Finder で削除することもできます。Finder のメニューバーで **移動** > **フォルダへ移動…** を選び、上記のパスを入力して該当フォルダーをゴミ箱に移動してください。`/Library` フォルダーの操作には管理者パスワードが必要です。

### 2. AudioUnit キャッシュのリセット

macOS は AudioUnit プラグインの情報をキャッシュしています。プラグイン ファイルを削除した後、キャッシュが残っていると DAW のプラグイン一覧に MuteKeeper が表示され続けることがあります。

通常はプラグイン ファイルの削除後に DAW を再起動すれば自動的にキャッシュが更新されますが、表示が残る場合は以下の手順でキャッシュをリセットしてください。

```bash
# AudioUnit キャッシュを削除
rm -rf ~/Library/Caches/AudioUnitCache/

# AudioComponentRegistrar を再起動（自動的に再起動されます）
killall -9 AudioComponentRegistrar
```

リセット後、DAW を再起動するとプラグインの再スキャンが行われます。

!!! note "AUv3 の登録解除について"
    AUv3 プラグインは macOS の PluginKit によって管理されています。Standalone アプリ（`/Applications/MuteKeeper.app`）を削除すれば、PluginKit の登録も自動的に解除されます。即座に反映されない場合は、ログアウトまたは再起動を行ってください。

### 3. 設定ファイルの削除（任意）

MuteKeeper の設定ファイルは以下に保存されています。完全に削除したい場合はこれらも削除してください。残しておいても問題はありません。

```bash
rm -f ~/Library/Preferences/to.kawa.MuteKeeper.plist
```

---

## DAW 側の設定について

一部の DAW では、プラグインのブロックリストやお気に入り等の設定に MuteKeeper の情報が残ることがあります。これらは DAW 側の設定であり、各 DAW のプラグイン管理機能から個別に削除してください。
