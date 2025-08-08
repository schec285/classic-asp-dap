Classic ASP用のVSCode Debug Adapterを作るために読むべきドキュメントをまとめます。

## 1. VSCode Debug Adapter Protocol (DAP) 関連

### 必須
- **[Debug Adapter Protocol Specification](https://microsoft.github.io/debug-adapter-protocol/specification)**
  - DAPの完全な仕様書
- **[VSCode Debugger Extension Guide](https://code.visualstudio.com/api/extension-guides/debugger-extension)**
  - VSCodeでのデバッガー拡張機能の作り方
- **[VSCode Debug Adapter Examples](https://github.com/microsoft/vscode-debugadapter-node/tree/main/examples)**
  - 実装サンプル集

### 参考実装
- **[vscode-node-debug2](https://github.com/microsoft/vscode-node-debug2)**
  - Node.jsデバッガーの実装（参考になる）
- **[vscode-php-debug](https://github.com/xdebug/vscode-php-debug)**
  - 別言語のDebug Adapter実装例

## 2. Windows デバッグ API

### 必須
- **[Windows Debugging API Overview](https://docs.microsoft.com/en-us/windows/win32/debug/debugging-functions)**
  - プロセスアタッチの基本
- **[Debug Interface Access SDK](https://docs.microsoft.com/en-us/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk)**
  - シンボル情報へのアクセス

### IISとASP関連
- **[IIS Architecture](https://docs.microsoft.com/en-us/iis/get-started/introduction-to-iis/introduction-to-iis-architecture)**
  - w3wp.exeの動作理解
- **[Debugging Script with the Microsoft Script Debugger](https://docs.microsoft.com/en-us/previous-versions/windows/desktop/ms690852(v=vs.85))**
  - 古いが重要な資料

## 3. COM/スクリプトデバッグ インターフェース

### 必須（古いドキュメント）
- **[Active Script Debugging API](https://docs.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/windows-scripting/reference/active-script-debugging-api-reference)**
- **[IActiveScriptDebug Interface](https://docs.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/windows-scripting/reference/iactivescriptdebug-interface)**
- **[Process Debug Manager Interfaces](https://docs.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/windows-scripting/reference/process-debug-manager-interfaces)**

## 4. Node.js ネイティブモジュール開発

### Node.jsからWindows APIを呼ぶため
- **[Node.js N-API Documentation](https://nodejs.org/api/n-api.html)**
  - ネイティブアドオンの作成
- **[node-gyp Documentation](https://github.com/nodejs/node-gyp)**
  - C++アドオンのビルドツール
- **[node-ffi-napi](https://github.com/node-ffi-napi/node-ffi-napi)**
  - 別の選択肢：FFIでWindows APIを直接呼ぶ

## 5. 実装の参考になるプロジェクト

### デバッグ関連
- **[WinDbg JavaScript Scripting](https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/javascript-debugger-scripting)**
  - Windows デバッガーのスクリプティング
- **[IISNode Source Code](https://github.com/tjanczuk/iisnode)**
  - IISとNode.jsの統合（アーキテクチャ参考）

### Classic ASP関連
- **[Classic ASP Debugging in VS](https://docs.microsoft.com/en-us/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications)**
  - Visual Studioでの実装参考

## 6. 追加で役立つリソース

### コミュニティ・フォーラム
- **[VSCode Extension Development Slack](https://aka.ms/vscode-dev-community)**
- **[VSCode GitHub Discussions](https://github.com/microsoft/vscode/discussions)**

### デバッグプロトコルの理解
- **[Chrome DevTools Protocol](https://chromedevtools.github.io/devtools-protocol/)**
  - 別のデバッグプロトコルの例（比較用）

## 読む順番の推奨

1. **VSCode Debugger Extension Guide** → 全体像を掴む
2. **Debug Adapter Protocol Specification** → プロトコルを理解
3. **vscode-node-debug2のソース** → 実装パターンを学ぶ
4. **Active Script Debugging API** → Classic ASP特有の部分
5. **Windows Debugging API** → プロセスアタッチの詳細

## 注意点

- Classic ASP/IScriptDebugger関連のドキュメントは多くが「Previous versions」にある
- Internet Archiveで古いMSDNドキュメントを探す必要があるかも
- 実際のCOMインターフェースの定義は Windows SDKのヘッダーファイルを見る必要がある
