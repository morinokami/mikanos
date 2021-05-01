## 資料

* MikanOS ソースコード: https://github.com/uchan-nos/mikanos
* MikanOS 開発環境: https://github.com/uchan-nos/mikanos-build
* サポートサイト: http://zero.osdev.jp (https://github.com/uchan-nos/os-from-zero)
* 東京工業大学 システム開発プロジェクト: https://www.youtube.com/channel/UCJx-rgFp80y-x7_JeBJ35yA

## 準備

```sh
$ git clone git@github.com:morinokami/osbook.git
$ cd osbook/devenv
$ python -m venv venv
$ source venv/bin/activate
$ pip install ansible
$ ansible-playbook -K -i ansible_inventory ansible_provision.yml
$ cd edk2
$ ln -s /path/to/mikanos/MikanLoaderPkg ./
$ source edksetup.sh
$ vim Conf/target.txt # https://github.com/uchan-nos/mikanos-build#%E3%83%96%E3%83%BC%E3%83%88%E3%83%AD%E3%83%BC%E3%83%80%E3%83%BC%E3%81%AE%E3%83%93%E3%83%AB%E3%83%89
$ build
$ ls Build/MikanLoaderX64/DEBUG_CLANG38/X64/Loader.efi
```

## ブートローダのビルド

```sh
$ cd devenv/edk2
$ source edksetup.sh
$ build
```

## カーネルのビルド

```sh
$ source devenv/buildenv.sh
$ cd mikanos/kernel
$ make
```


## 実行

```
$ ./devenv/run_qemu.sh ./devenv/edk2/Build/MikanLoaderX64/DEBUG_CLANG38/X64/Loader.efi ./mikanos/kernel/kernel.elf
```