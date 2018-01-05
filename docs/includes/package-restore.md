- **パッケージ マネージャー UI** (Visual Studio): ソリューション エクスプローラーのソリューションを右クリックして、**[NuGet パッケージの復元]** を選択します。 1 つまたは複数の個別のパッケージが、まだ適切にインストールされない場合 (ソリューション エクスプローラーにエラー アイコンが表示される)、パッケージ マネージャー UI を使用し、影響を受けるパッケージをアンインストールして再インストールします。 「[パッケージの再インストールと更新](../Consume-Packages/Reinstalling-and-Updating-Packages.md)」を参照してください。

- **コマンド ライン**: [nuget restore](../tools/cli-ref-restore.md) コマンドを使用します。 プロジェクト フォルダーで `nuget restore` を実行するだけで、プロジェクトの依存関係を復元しようとします。