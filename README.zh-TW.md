# sway

sway 是一個與 [i3](https://i3wm.org/) 相容的 [Wayland](http://wayland.freedesktop.org/) compositor。
閱讀 [FAQ](https://github.com/swaywm/sway/wiki)。 加入 [IRC
頻道](http://webchat.freenode.net/?channels=sway&uio=d4) (#sway on
irc.freenode.net)

如果你想支持 sway 的開發，請到 [SirCmpwn's
Patreon page](https://patreon.com/sircmpwn) 貢獻。

## 發行簽章

所有發行的版本都會以 [B22DA89A](http://pgp.mit.edu/pks/lookup?op=vindex&search=0x52CB6609B22DA89A) 簽署
並發佈於 [GitHub](https://github.com/swaywm/sway/releases)

## 安裝

### 從套件安裝

Sway 在許多發行版都有提供。請自己嘗試於你的發行版安裝 「sway」這個套件。
如果無法取得，請查看 [這個 wiki 頁面](https://github.com/swaywm/sway/wiki/Unsupported-packages)
以取得更多關於如何於你使用的發行版上安裝的資訊。

如果你想要為你使用的發行版包裝 sway，請到 IRC 頻道或是直接寄封信到 sir@cmpwn.com 來取得一些建議。

### 從原始碼編譯

相依套件:

* meson \*
* [wlroots](https://github.com/swaywm/wlroots)
* wayland
* wayland-protocols \*
* pcre
* json-c
* pango
* cairo
* gdk-pixbuf2 (選擇性: system tray)
* [scdoc](https://git.sr.ht/~sircmpwn/scdoc) (選擇性: man pages) \*
* git \*

_\*編譯時相依_

執行這些指令:

    meson build
    ninja -C build
    sudo ninja -C build install

在沒有 logind 的系統上，你需要為 sway 的執行檔加上 suid。

    sudo chmod a+s /usr/local/bin/sway

Sway 在啟動不久後就會放棄 root 權限。

## 設定檔

如果你已經在使用 i3，你可以直接將你的 i3 設定檔複製到 `~/.config/sway/config` 然後就能直接使用。
或者你也可以把範例設定檔複製到 `~/.config/sway/config`。 它通常會在 `/etc/sway/config`。
執行 `man 5 sway` 來取得更多關於設定檔的資訊。

## 執行

在 TTY 執行 `sway`。有些 display manager 可能可以運作但 sway 不提供支援 (已知 gdm 運作的很好)
