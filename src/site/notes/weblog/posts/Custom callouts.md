---
{"dg-publish":true,"dg-path":"posts/Custom callouts.md","dg-permalink":"custom-callouts","permalink":"/custom-callouts/"}
---


Custom callouts for [Obsidian](https://obsidian.md) inspired by [Flexoki](https://stephango.com/flexoki) theme!

## Installation

1. Copy [[weblog/posts/Custom callouts#^757380\|this code]] and create `file.css`.
2. Go to **Obsidian → Settings → Appearance → CSS snippets**.
3. Open snippets folder and paste the file there.

---

> [!pink]- **Pink**
> `> [!pink]`

> [!accessibility]- **Accessibility**
> `> [!accessibility]`

> [!purple]- **Purple**
> `> [!purple]`

> [!book]- **Book**
> `> [!book]`

> [!bot]- **Bot**
> `> [!bot]`

> [!calculator]- **Calculator**
> `> [!calculator]`

> [!camera]- **Camera**
> `> [!camera]`

> [!clipboard]- **Clipboard**
> `> [!clipboard]`

> [!clock]- **Clock**
> `> [!clock]`

> [!film]- **Film**
> `> [!film]`

> [!gamepad]- **Gamepad**
> `> [!gamepad]`

> [!headphones]- **Headphones**
> `> [!headphones]`

> [!hourglass]- **Hourglass**
> `> [!hourglass]`

> [!keyboard]- **Keyboard**
> `> [!keyboard]`

> [!laptop]- **Laptop**
> `> [!laptop]`

> [!mic]- **Mic**
> `> [!mic]`

> [!monitor]- **Monitor**
> `> [!monitor]`

> [!mouse]- **Mouse**
> `> [!mouse]`

> [!settings]- **Settings**
> `> [!settings]`

> [!smartphone]- **Smartphone**
> `> [!smartphone]`

> [!tablet]- **Tablet**
> `> [!tablet]`

> [!tv]- **Tv**
> `> [!tv]`

> [!video]- **Video**
> `> [!video]`

> [!blue]- **Blue**
> `> [!blue]`

> [!bluetooth]- **Bluetooth**
> `> [!bluetooth]`

> [!bookmark]- **Bookmark**
> `> [!bookmark]`

> [!calendar]- **Calendar**
> `> [!calendar]`

> [!contact]- **Contact**
> `> [!contact]`

> [!link]- **Link**
> `> [!link]`

> [!mail]- **Mail**
> `> [!mail]`

> [!printer]- **Printer**
> `> [!printer]`

> [!weather]- **Weather**
> `- [!weather]`

> [!winter]- **Winter**
> `> [!winter]`

> [!user]- **User**
> `> [!user]`

> [!cyan]- **Cyan**
> `> [!cyan]`

> [!archive]- **Archive**
> `> [!archive]`

> [!at]- **At**
> `> [!at]`

> [!compass]- **Compass**
> `> [!compass]`

> [!connect]- **Connect**
> `> [!connect]`

> [!download]- **Download**
> `> [!download]`

> [!file]- **File**
> `> [!file]`

> [!folder]- **Folder**
> `> [!folder]`

> [!globe]- **Globe**
> `> [!globe]`

> [!image]- **Image**
> `> [!image]`

> [!infinity]- **Infinity**
> `> [!infinity]`

> [!languages]- **Languages**
> `> [!languages]`

> [!music]- **Music**
> `> [!music]`

> [!package]- **Package**
> `> [!package]`

> [!save]- **Save**
> `> [!save]`

> [!search]- **Search**
> `> [!search]`

> [!share]- **Share**
> `> [!share]`

> [!tag]- **Tag**
> `> [!tag]`

> [!trash]- **Trash**
> `> [!trash]`

> [!upload]- **Upload**
> `> [!upload]`

> [!wallet]- **Wallet**
> `> [!wallet]`

> [!green]- **Green**
> `> [!green]`

> [!banknote]- **Banknote**
> `> [!banknote]`

> [!battery]- **Battery**
> `> [!battery]`

> [!home]- **Home**
> `> [!home]`

> [!network]- **Network**
> `> [!network]`

> [!phone]- **Phone**
> `> [!phone]`

> [!spring]- **Spring**
> `> [!spring]`

> [!yellow]- **Yellow**
> `> [!yellow]`

> [!inbox]- **Inbox**
> `> [!inbox]`

> [!star]- **Star**
> `> [!star]`

> [!summer]- **Summer**
> `> [!summer]`

> [!orange]- **Orange**
> `> [!orange]`

> [!alarm]- **Alarm**
> `> [!alarm]`

> [!bell]- **Bell**
> `> [!bell]`

> [!fall]- **Fall**
> `> [!fall]`

> [!flag]- **Flag**
> `> [!flag]`

> [!rss]- **Rss**
> `> [!rss]`

> [!red]- **Red**
> `> [!red]`

> [!delete]- **Delete**
> `> [!delete]`

> [!fuel]- **Fuel**
> `> [!fuel]`

> [!heart]- **Heart**
> `> [!heart]`

> [!location]- **Location**
> `> [!location]`

> [!pin]- **Pin**
> `> [!pin]`

> [!power]- **Power**
> `> [!power]`

> [!shield]- **Shield**
> `> [!shield]`

---

> [!facebook]- **Facebook**
> `> [!facebook]`

> [!github]- **GitHub**
> `> [!github]`

> [!instagram]- **Instagram**
> `> [!instagram]`

> [!linkedin]- **Linkedin**
> `> [!linkedin]`

> [!twitch]- **Twitch**
> `> [!twitch]`

> [!twitter]- **Twitter**
> `> [!twitter]`

> [!youtube]- **YouTube**
> `> [!youtube]`

---

## CSS code
{ #757380}


```css
.callout[data-callout="pink"] { --callout-color: 206, 93, 151; --callout-icon: none; }
.callout[data-callout="accessibility"] { --callout-color: 206, 93, 151; --callout-icon: accessibility; }

.callout[data-callout="purple"] { --callout-color: 139, 126, 200; --callout-icon: none; }
.callout[data-callout="book"] { --callout-color: 139, 126, 200; --callout-icon: book; }
.callout[data-callout="bot"] { --callout-color: 139, 126, 200; --callout-icon: bot; }
.callout[data-callout="calculator"] { --callout-color: 139, 126, 200; --callout-icon: calculator; }
.callout[data-callout="calendar"] { --callout-color: 139, 126, 200; --callout-icon: calendar; }
.callout[data-callout="camera"] { --callout-color: 139, 126, 200; --callout-icon: camera; }
.callout[data-callout="clipboard"] { --callout-color: 139, 126, 200; --callout-icon: clipboard; }
.callout[data-callout="clock"] { --callout-color: 139, 126, 200; --callout-icon: clock; }
.callout[data-callout="film"] { --callout-color: 139, 126, 200; --callout-icon: film; }
.callout[data-callout="gamepad"] { --callout-color: 139, 126, 200; --callout-icon: gamepad-2; }
.callout[data-callout="headphones"] { --callout-color: 139, 126, 200; --callout-icon: headphones; }
.callout[data-callout="hourglass"] { --callout-color: 139, 126, 200; --callout-icon: hourglass; }
.callout[data-callout="keyboard"] { --callout-color: 139, 126, 200; --callout-icon: keyboard; }
.callout[data-callout="laptop"] { --callout-color: 139, 126, 200; --callout-icon: laptop; }
.callout[data-callout="mic"] { --callout-color: 139, 126, 200; --callout-icon: mic; }
.callout[data-callout="monitor"] { --callout-color: 139, 126, 200; --callout-icon: monitor; }
.callout[data-callout="mouse"] { --callout-color: 139, 126, 200; --callout-icon: mouse; }
.callout[data-callout="settings"] { --callout-color: 139, 126, 200; --callout-icon: settings; }
.callout[data-callout="smartphone"] { --callout-color: 139, 126, 200; --callout-icon: smartphone; }
.callout[data-callout="tablet"] { --callout-color: 139, 126, 200; --callout-icon: tablet; }
.callout[data-callout="tv"] { --callout-color: 139, 126, 200; --callout-icon: tv; }
.callout[data-callout="video"] { --callout-color: 139, 126, 200; --callout-icon: video; }

.callout[data-callout="blue"] { --callout-color: 67, 133, 190; --callout-icon: none; }
.callout[data-callout="bluetooth"] { --callout-color: 67, 133, 190; --callout-icon: bluetooth; }
.callout[data-callout="bookmark"] { --callout-color: 67, 133, 190; --callout-icon: bookmark; }
.callout[data-callout="contact"] { --callout-color: 67, 133, 190; --callout-icon: contact; }
.callout[data-callout="link"] { --callout-color: 67, 133, 190; --callout-icon: link; }
.callout[data-callout="mail"] { --callout-color: 67, 133, 190; --callout-icon: mail; }
.callout[data-callout="printer"] { --callout-color: 67, 133, 190; --callout-icon: printer; }
.callout[data-callout="winter"] { --callout-color: 67, 133, 190; --callout-icon: snowflake; }
.callout[data-callout="user"] { --callout-color: 67, 133, 190; --callout-icon: user; }

.callout[data-callout="cyan"] { --callout-color: 58, 169, 159; --callout-icon: none; }
.callout[data-callout="archive"] { --callout-color: 58, 169, 159; --callout-icon: archive; }
.callout[data-callout="at"] { --callout-color: 58, 169, 159; --callout-icon: at-sign; }
.callout[data-callout="compass"] { --callout-color: 58, 169, 159; --callout-icon: compass; }
.callout[data-callout="connect"] { --callout-color: 58, 169, 159; --callout-icon: share-2; }
.callout[data-callout="download"] { --callout-color: 58, 169, 159; --callout-icon: download; }
.callout[data-callout="file"] { --callout-color: 58, 169, 159; --callout-icon: file; }
.callout[data-callout="folder"] { --callout-color: 58, 169, 159; --callout-icon: folder; }
.callout[data-callout="globe"] { --callout-color: 58, 169, 159; --callout-icon: globe; }
.callout[data-callout="image"] { --callout-color: 58, 169, 159; --callout-icon: image; }
.callout[data-callout="infinity"] { --callout-color: 58, 169, 159; --callout-icon: infinity; }
.callout[data-callout="languages"] { --callout-color: 58, 169, 159; --callout-icon: languages; }
.callout[data-callout="music"] { --callout-color: 58, 169, 159; --callout-icon: music; }
.callout[data-callout="package"] { --callout-color: 58, 169, 159; --callout-icon: package; }
.callout[data-callout="save"] { --callout-color: 58, 169, 159; --callout-icon: save; }
.callout[data-callout="search"] { --callout-color: 58, 169, 159; --callout-icon: search; }
.callout[data-callout="share"] { --callout-color: 58, 169, 159; --callout-icon: share; }
.callout[data-callout="tag"] { --callout-color: 58, 169, 159; --callout-icon: tag; }
.callout[data-callout="trash"] { --callout-color: 58, 169, 159; --callout-icon: trash; }
.callout[data-callout="upload"] { --callout-color: 58, 169, 159; --callout-icon: upload; }
.callout[data-callout="wallet"] { --callout-color: 58, 169, 159; --callout-icon: wallet; }

.callout[data-callout="green"] { --callout-color: 135, 154, 57; --callout-icon: none; }
.callout[data-callout="banknote"] { --callout-color: 135, 154, 57; --callout-icon: banknote; }
.callout[data-callout="battery"] { --callout-color: 135, 154, 57; --callout-icon: battery; }
.callout[data-callout="home"] { --callout-color: 135, 154, 57; --callout-icon: home; }
.callout[data-callout="network"] { --callout-color: 135, 154, 57; --callout-icon: network; }
.callout[data-callout="phone"] { --callout-color: 135, 154, 57; --callout-icon: phone; }
.callout[data-callout="spring"] { --callout-color: 135, 154, 57; --callout-icon: flower-2; }

.callout[data-callout="yellow"] { --callout-color: 208, 162, 21; --callout-icon: none; }
.callout[data-callout="inbox"] { --callout-color: 208, 162, 21; --callout-icon: inbox; }
.callout[data-callout="star"] { --callout-color: 208, 162, 21; --callout-icon: star; }
.callout[data-callout="summer"] { --callout-color: 208, 162, 21; --callout-icon: sun; }

.callout[data-callout="orange"] { --callout-color: 218, 112, 44; --callout-icon: none; }
.callout[data-callout="alarm"] { --callout-color: 218, 112, 44; --callout-icon: alarm-clock; }
.callout[data-callout="bell"] { --callout-color: 218, 112, 44; --callout-icon: bell; }
.callout[data-callout="fall"] { --callout-color: 218, 112, 44; --callout-icon: leaf; }
.callout[data-callout="flag"] { --callout-color: 218, 112, 44; --callout-icon: flag; }
.callout[data-callout="rss"] { --callout-color: 218, 112, 44; --callout-icon: rss; }

.callout[data-callout="red"] { --callout-color: 209, 77, 65; --callout-icon: none; }
.callout[data-callout="delete"] { --callout-color: 209, 77, 65; --callout-icon: delete; }
.callout[data-callout="fuel"] { --callout-color: 209, 77, 65; --callout-icon: fuel; }
.callout[data-callout="heart"] { --callout-color: 209, 77, 65; --callout-icon: heart; }
.callout[data-callout="location"] { --callout-color: 209, 77, 65; --callout-icon: map-pin; }
.callout[data-callout="pin"] { --callout-color: 209, 77, 65; --callout-icon: pin; }
.callout[data-callout="power"] { --callout-color: 209, 77, 65; --callout-icon: power; }
.callout[data-callout="shield"] { --callout-color: 209, 77, 65; --callout-icon: shield; }

.callout[data-callout="discord"] { --callout-color: 88, 101, 242; --callout-icon: discord; }
.callout[data-callout="facebook"] { --callout-color: 24, 119, 242; --callout-icon: facebook; }
.callout[data-callout="github"] { --callout-color: 64, 120, 192; --callout-icon: github; }
.callout[data-callout="instagram"] { --callout-color: 255, 0, 105; --callout-icon: instagram; }
.callout[data-callout="linkedin"] { --callout-color: 10, 102, 194; --callout-icon: linkedin; }
.callout[data-callout="twitch"] { --callout-color: 145, 70, 255; --callout-icon: twitch; }
.callout[data-callout="twitter"] { --callout-color: 29, 161, 242; --callout-icon: twitter; }
.callout[data-callout="youtube"] { --callout-color: 255, 0, 0; --callout-icon: youtube; }
```
