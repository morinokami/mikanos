* osbook
  * devenv
    * edk2: UEFI BIOS 自体の開発にも、UEFI BIOS 上で動くアプリケーションの開発にも使うことができる開発キット
      * Build
        * MikanLoaderX64/DEBUG_CLANG38/X64/Loader.efi
      * Conf
        * target.txt: ビルド設定
        * tools_def.txt: ツールチェーンの設定
      * MdePkg: EDK の中心的ライブラリのパッケージディレクトリ
      * OvmfPkg: UEFI BIOS のオープンソース実装である OVMF
    * run_qemu.sh: QEMU を起動する
  * mikanos
    * kernel: カーネル
      * main.cpp
      * MakeFile
    * MikanLoaderPkg: ブートローダ
      * Loader.inf: コンポーネント定義ファイル (エントリポイントを記述)
      * Main.c
      * MikanLoaderPkg.dec: パッケージ宣言ファイル
      * MikanLoaderPkg.dsc: パッケージ記述ファイル