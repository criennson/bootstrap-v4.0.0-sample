# Bootstrap 3->4差分メモ

https://v4-alpha.getbootstrap.com/migration/
## 全体的な変更
```
Flexbox is enabled by default. In general this means a move away from floats and more across our components.
```
Gridがfloatからflexboxへ変更

```
Switched from Less to Sass for our source CSS files.
```
LessからSassに変更

```
Switched from px to rem as our primary CSS unit, though pixels are still used for media queries and grid behavior as viewports are not affected by type size.
```
CSSのサイズ指定がpxからrem指定になった

```
Global font-size increased from 14px to 16px.
```
フォントサイズの基準がちょっと大きく
(14px -> 16px)

```
Added a new grid tier for smaller devices at 576px and below (our new xs tier).
```
Gridとかで使うサイズ指定がちょいと変更
v3の.col-md-6がv4の.col-lg-6になる
xs：768px未満 -> 576px未満のディスプレイ向け

```
Replaced the separate optional theme with configurable options via SCSS variables (e.g., $enable-gradients: true).
```
なんか書き換わったみたい・・・？（コードは追えていない

---
## その他の変更
### Grid system
https://v4-alpha.getbootstrap.com/layout/grid/
```
@include media-breakpoint-up(sm) { ... }
@include media-breakpoint-down(sm) { ... }
```
みたいな@media使える便利なやつがある

```
.justify-content-md-center
```
row内col中央揃え！
flexboxなので縦中央も調整しやすいはず。
flexboxでできることはこちら https://codepen.io/enxaneta/full/adLPwv/

### Components
```
Dropped panels, thumbnails, and wells for a new all-encompassing component, cards.
```
panels、thumbnails、wellsがなくなってcardsに統合されたりしてます
```
Dropped the Glyphicons icon font. If you need icons, some options are:
   the upstream version of Glyphicons
   Octicons
   Font Awesome
```
今までのGlyphiconsじゃなくなった・・・？
```
Dropped the Affix jQuery plugin. We recommend using a position: sticky polyfill instead. See the HTML5 Please entry for details and specific polyfill recommendations.
If you were using Affix to apply additional, non-position styles, the polyfills might not support your use case. One option for such uses is the third-party ScrollPos-Styler library.
```
position: fixed から position: sticky使おうぜ！っていう風になった
```
Dropped the pager component as it was essentially slightly customized buttons.
```
pagerなくなった
```
Refactored nearly all components to use more un-nested classes instead of children selectors.
```
ネスト時も使いやすくなった？（未検証

### Typography
https://v4-alpha.getbootstrap.com/content/typography/
便利クラス増えた
`.blockquote-reverse`  -> 引用元紹介とかに使えそうな右揃えブロック
`text-uppercase` -> 全部大文字
など