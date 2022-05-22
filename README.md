# Ansible Role: disable-swap

Linux サーバの Swap を無効化します。

この role では次のことを行います。

* Swap の無効化。
* /etc/fstab からの Swap マウント設定の削除。
* Swap file の削除。
* Kernel parameter (vm.swappiness = 0) の設定。

この role では次のことを行いません。

* Swap パーティションの削除。

## Requirements

この role には特別な要件はありません。

## Role Variables

```yaml
disable_swap_list: []
```

無効化する swap のファイル名やデバイス名をリストで指定してください。
`disable_swap_list` が定義されていない場合は、全ての Swap が無効化の対象になります。

その他の variables は [defaults/main.yml](defaults/main.yml) を参照してください。

## Dependencies

None.

## Example Playbook

```yaml
- hosts: your-linux-servers
  roles:
    - ktooi.disable-swap
```

## Authors

* **Kodai Tooi** [GitHub](https://github.com/ktooi), [Qiita](https://qiita.com/ktooi)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
