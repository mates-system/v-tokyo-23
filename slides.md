---
background: https://cover.sli.dev
title: インタラクティブな ICT 教材の実装に DSL で立ち向かう
info: |
  ## インタラクティブな ICT 教材の実装に DSL で立ち向かう
  「Vue.js の活用事例特集」
transition: slide-left
fonts:
  sans: Noto Sans JP
  mono: Input Mono, monospace
theme: ./theme
---

<h1>
  <span class="line-1"><span class="accent">インタラクティブ</span>な</span>
  <br />
  <span class="line-2"><span class="accent">ICT教材</span>の実装に</span>
  <br />
  <span class="line-3"><span class="accent">DSL</span>で立ち向かう</span>
</h1>

<p class="abs-bl left-14 bottom-6">
  <a href="https://vuejs-meetup.connpass.com/event/355473/" class="flex gap-3 items-center"><img src="/vuejs-jp.png" alt="v-tokyo" class="w-10 pt-2" />v-tokyo #23</a>
</p>
<p class="abs-br right-14 bottom-6"><a href="https://x.com/naitokosuke">@naitokosuke</a></p>

<style>
h1 {
  margin-top: 2rem;
  font-size: 6rem !important;
  font-weight: 1000;
  line-height: 1.25;

  span {
    color: white;
  }

  .accent {
    color: color-mix(in srgb, var(--slidev-theme-primary), black 10%);
    font-weight: 1000;
  }

  .line-2 { letter-spacing: 1.05rem }
  .line-3 { letter-spacing: 0.82rem }
}

p {
  font-size: 2.25rem;
  font-weight: 1000;
  color: color-mix(in srgb, var(--slidev-theme-primary), black 10%);
}
</style>

---
layout: center
class: text-center
transition: slide-up
---

<div class="relative inline-block">
  <img src="/japanese-companies-using-vuejs.png" alt="[https://github.com/chibivue-land/japanese-companies-using-vuejs の OGP]" class="mx-auto h-130" />
  <a href="https://github.com/chibivue-land/japanese-companies-using-vuejs">
    <img src="/qr-japanese-companies-using-vuejs.png" alt="[https://github.com/chibivue-land/japanese-companies-using-vuejs の QR コード]" class="absolute bottom-4 right-10 z-10 w-70 screen-shot-embed" />
  </a>
</div>

<!--
突然ですが、みなさん、chibivue-land/japanese-companies-using-vuejs っていうリポジトリをご存知でしょうか？

このリポジトリは、chibivue land という Vue.js コミュニティ発のプロジェクトで、日本で Vue.js を採用している企業のリストを集めたリポジトリになっています。

ぜひ PR を送ってみてください〜
-->

---

<img src="/mates-on-japanese-companies-using-vuejs.png" alt="[https://github.com/chibivue-land/japanese-companies-using-vuejs に株式会社メイツが載っているスクショ]" class="flex items-center mx-auto screen-shot-embed" />

<div
  class="animated-ellipse"
  style="top: 54%; left: 8%; width: 594px; height: 90px;"
/>

<img src="/mates-logo.png" alt="株式会社メイツ" class="absolute bottom-66 left-140 w-36 mates-logo" />

<style scoped>
.animated-ellipse {
  @apply absolute border-4 border-red-500;
  transform: scale(0);
  animation: pop-in 0.4s ease-out forwards;
  animation-delay: 1s;
  transform-origin: center;
}
@keyframes pop-in {
  0% { transform: scale(0); opacity: 0; }
  60% { transform: scale(1.2); opacity: 1; }
  100% { transform: scale(1); }
}

img.mates-logo {
  transform: scale(0);
  animation: pop-in 0.4s ease-out forwards;
  animation-delay: 1s;
  transform-origin: center;
}
</style>

<!--
弊社株式会社メイツが一番上に載っているんです！

弊社も Vue.js で開発を行なっています。
-->

---
layout: center
class: text-center
transition: slide-up
---

<h1>株式会社メイツ</h1>

<p :class="$slidev.nav.clicks === 1 ? 'clicked' : ''">一言で表すと</p>

<img src="/edutech.png" alt="edutech" class="mx-auto my-4 px-4" :class="$slidev.nav.clicks === 1 ? 'clicked' : ''" />

<div
  v-if="$slidev.nav.clicks === 1"
  class="overlay"
>
  <img src="/aim-at-logo.png" alt="aim@" class="mx-auto my-4" />
  <img src="/reco-logo.png" alt="reco" class="mx-auto my-4 w-50" />
</div>

<div style="display: none;" v-click />

<style scoped>
p.clicked { color: var(--slidev-theme-background); }
img.clicked { filter: blur(40px); }

.overlay {
  top: 5vh;
}
</style>

<!--
さて、そんな Vue.js を採用している株式会社メイツですが、弊社を一言で表すと...

EdTech 企業です。
教育×テクノロジーで学習を支援しています。

(クリック)

主なプロダクトは 2 つ、aim@ と reco。

どちらも Vue、Nuxt で開発されています。今日は特に aim@ での Vue.js 活用事例についてお話しさせていただきます。
-->

---
layout: center
---

<div class="flex items-center gap-12">
  <div class="flex-shrink-0">
    <a href="https://x.com/naitokosuke"><img src="/naitokosuke-sns-icon.png" class="w-56 h-56 rounded-full shadow-lg" /></a>
  </div>
  <div class="flex-1">
    <h2 class="text-5xl font-bold mb-6">ナイトウコウスケ</h2>
    <ul class="space-y-3 text-3xl">
      <li class="flex items-center">
        <span class="text-[#42b883] mr-2">▸</span>
        Compostion API 生まれ script setup 育ち
      </li>
      <li class="flex items-center">
        <span class="text-[#35495e] mr-2">▸</span>
        <logos-vue class="h-7 mt-1 mr-2" /> 3.2+
      </li>
    </ul>
    <div class="mt-8 pt-6 border-t border-gray-200">
      <p class="text-2xl text-gray-600">
        株式会社メイツ (2025.02~) <img src="/mates-logo.png" class="ml-2 h-10 inline-block" /><br/>
        フロントエンドエンジニア
      </p>
    </div>
  </div>
</div>

<!--
ここで簡単に自己紹介をさせてください。

ナイトウコウスケと申します。

Composition API 生まれ、script setup 育ちということでやらせてもらっています。

2025 年 2 月から株式会社メイツにフロントエンドエンジニアとして入社しました。
-->

---
layout: center
---

<h1 class="text-8xl leading-36 font-bold mb-0">インタラクティブな<br /> ICT 教材の実装に<br /> DSL で立ち向かう</h1>

<div class="overlay overlay-white" v-click>
  <div>
    <h2 class="text-6xl">今日話すこと</h2>
    <ul class="mx-12 list-disc">
      <li class="text-5xl/24">株式会社メイツ</li>
      <li class="text-5xl/24">ICT 教材開発の課題</li>
      <li class="text-5xl/24">aim@ contents definition language</li>
    </ul>
  </div>
</div>

<style scoped>
.overlay { padding: 0 16px; }
</style>

<!--
「インタラクティブな ICT 教材の実装に DSL で立ち向かう」ということで、

（クリック）

今日お話しする内容は大きく 3 つです。

1つ目が株式会社メイツについて。
スライドの理解の補足程度に弊社について紹介させてください。

2つ目が  ICT 教材開発の課題。

そして3つ目が、その課題をどう解決したか、そのキーワードである aim@ contents definition language についてです。

Vue.js をどう活用して、複雑な要件に対応したか、実装の裏側までお見せしたいと思います。

それでは、まず株式会社メイツについて詳しくご紹介させてください。
-->

---
layout: section
---

<h1 class="flex items-center justify-center text-8xl gap-4">
  <span>株式会社メイツ</span>
  <img src="/mates-logo.png" alt="mates inc." class="w-24 mt-4" />
</h1>

<!--
では、改めて株式会社メイツについて詳しくご紹介します。
-->

---
transition: slide-up
---

<div class="grid gap-4 grid-cols-3 items-center text-5xl my-20">
  <ul class="grid gap-12">
    <li class="font-bold underline underline-#D79A02 underline-offset-8">学習塾事業</li>
    <li class="font-bold underline underline-#e82518 underline-offset-8">アプリ事業</li>
  </ul>

  <img src="/mates-teams.svg" alt="[メイツの事業概要図]" class="col-span-2" />
</div>

<!--
メイツは主に 2 つの事業を展開しています。

学習塾事業、直営の学習塾を運営しています。

アプリ事業、ICT 教材の開発・販売を行っています。

右の図を見ていただくと、各チームの関係性がわかると思います。

私が所属しているのがシステム開発チーム。ここでエンジニアがプロダクト開発をしています。

アプリ事業チームは aim@ の営業・販促活動を担当。

コンテンツ開発チームは、実際の教材コンテンツを作っています。
-->

---

<h1 class="flex items-center mb-12">
  <img src="/aim-at-logo.png" alt="aim@" aria-hidden="true" class="w-56" />
</h1>

<div class="grid grid-cols-2 gap-8 items-center">
  <ul class="space-y-4 text-4xl">
    <template v-if="$slidev.nav.clicks === 0">
      <li>学習塾向け ICT 教材</li>
      <li>定期テスト、英検、<br />高校入試、etc...</li>
      <li>Web アプリケーション</li>
    </template>
    <template v-if="$slidev.nav.clicks === 1">
      <li class="flex items-center">Web アプリ <logos-vue class="ml-2 h-8" /></li>
      <li>豊富な問題/解答形式</li>
      <li>マルチデバイス (& PWA)</li>
      <li>時間管理、メディアストリーミング、etc...</li>
    </template>
  </ul>
  <div>
    <img
      src="/aim-at-image.png"
      alt="[aim@ のイメージ]"
      class="mx-auto max-h-96"
    />
  </div>
</div>

<div style="display: none;" v-click />

<!--
では、ここからはアプリ事業の主力プロダクトの aim@ について紹介します。

まず aim@ は学習塾向けの ICT 教材プラットフォームです。

定期テスト対策、英検対策、高校入試対策など、幅広い学習コンテンツを提供しています。

Web アプリケーションとして作られています。

（クリック）

エンジニアイベントということで、aim@ の技術的な側面、特徴について説明します

技術的な特徴としては、Vue.js で構築された SPA です。

そして、ここが今日の話のポイントなんですが、とにかく豊富な問題形式・解答形式に対応しているんです。

マルチデバイス対応もしていて、PC、タブレット、スマートフォンすべてで動きます。PWA 対応も行っています。

他にも時間管理機能やメディアストリーミング機能など、学習に必要な機能を色々実装しています。
-->

---
class: text-center
layout: section
transition: slide-up
---

<h1 class="text-6xl">学習教材のドメイン知識は複雑</h1>

<p class="text-5xl">(一般的な話)</p>

<!--
ここで皆さんに学習教材のことについて少し考えていただきたいです。
塾や学校で使ったことのある学習教材についてです。

学習教材のドメイン知識って、実はめちゃくちゃ複雑なんです。
-->

---
transition: slide-up
---

<div class="mx-auto grid items-center justify-center">
  <h1>多様な学習形式と多様な問題形式</h1>
  <div class="grid grid-cols-3 gap-16 mx-auto">
    <ul class="grid gap-6 text-3xl border border-lightblue-200 bg-lightblue-50 rounded-lg p-4 h-100">
      <li>テスト</li>
      <li>一問一答</li>
      <li>ドリル</li>
      <li>模試</li>
      <li>講義動画</li>
      <li>インプット教材</li>
    </ul>
    <div class="grid col-span-2 grid-cols-2 gap-16 border border-lightblue-200 bg-lightblue-50 rounded-lg p-4 h-100">
      <ul class="grid gap-4 text-3xl">
        <li>択一</li>
        <li>複数選択</li>
        <li>穴埋め</li>
        <li>長文記述</li>
        <li>正誤</li>
        <li>書き順</li>
        <li>並び替え</li>
      </ul>
      <ul class="grid gap-4 text-3xl">
        <li>数式</li>
        <li>画像問題</li>
        <li>長文読解</li>
        <li>グラフ</li>
        <li>リスニング</li>
        <li>スピーキング</li>
        <li>作文添削</li>
      </ul>
    </div>
  </div>
</div>

<!--
見てください、この多様性を。

左側が表現するならば学習形式です。

そして右側が問題形式。これがまた多い。

で、これらの組み合わせも考えられますよね。
テスト中の問題形式が全て同じとは限りませんよね。
-->

---
transition: slide-up
layout: center
class: text-center
---

<h2 class="flex items-center text-7xl">
  <img src="/aim-at-logo.png" class="aim-at-logo" alt="aim@" aria-hidden="true" />
  <span>で扱う問題形式</span>
</h2>

<style scoped>
.aim-at-logo {
  width: 240px;
  margin-right: 1rem;
}
</style>

<!--
aim@ では多様な学習形式、問題形式を対応しているのですが、今回の発表では問題形式に絞って説明していきます。

じゃあ実際に aim@ でどんな問題形式を扱っているか、いくつか  aim@ の学習画面イメージとともにピックアップして紹介します。
-->

---
transition: slide-up
---

<h1 class="text-7xl">ChoiceFormat</h1>

<div class="grid grid-cols-3 gap-4 text-3xl mt-12">
  <ul class="grid gap-4">
    <li>単一選択/複数選択</li>
    <li>複数重複選択</li>
    <li>選択肢の解除機能</li>
    <li>選択肢のシャッフル</li>
    <li>選択肢に数式</li>
    <li>解答欄の結合</li>
  </ul>
  <img
    src="/choice-format.png"
    alt="[選択式問題のスクリーンショット]"
    class="mx-auto col-span-2 screen-shot-embed"
  />
</div>

<!--
まず ChoiceFormat。選択式問題です。

単一選択と複数選択の切り替えはもちろん、複数重複選択っていうのもあって、これは同じ選択肢を何回も選べる機能です。

選択肢の解除もできます。間違えてタップしちゃったときとか。

さらに、選択肢のシャッフル機能。
解答の順番を覚える、学生の最終手段を対策する機能も。

選択肢に数式も表示できます。

解答欄の結合なんていうのもあって、これは一つの解答欄にカンマ区切りで解答を連ねる解答方法です。
-->

---
transition: slide-up
---

<h1 class="text-7xl">WriteFormat</h1>

<div class="grid grid-cols-3 gap-4 text-4xl mt-12">
  <ul class="grid gap-4">
    <li>textarea (作文)</li>
    <li>解答欄の伸び縮み</li>
    <li>解答欄のクリア</li>
  </ul>
  <img
    src="/write-format.png"
    alt="記述形式のスクリーンショット"
    class="mx-auto col-span-2 screen-shot-embed"
  />
</div>

<!--
次は WriteFormat。記述式問題です。

記述といっても答えだけ書くものとか作文のように長文回答もあります。

解答欄の伸び縮みもサポートしています。
いわゆる input 要素だと、長い入力を行うと最初に入力した文字が見えなくなったりしますよね。

解答欄のクリア機能も。
-->

---
transition: slide-up
---

<h1 class="text-5xl">KanjiHiraganaHandWritingFormat</h1>

<div class="grid grid-cols-3 gap-4 text-4xl mt-12">
  <ul class="grid text-5xl gap-4">
    <li>書き順</li>
    <li>消しゴム</li>
    <li>undo</li>
  </ul>
  <img
    src="/kanji-hiragana-hand-writing-format.png"
    alt="手書き形式のスクリーンショット"
    class="mx-auto col-span-2 screen-shot-embed"
  />
</div>

<!--
そして KanjiHiraganaHandWritingFormat。

漢字・ひらがなの手書き入力です。

aim＠ はタブレット学習も対応していて、
主にタブレット学習を想定した問題形式です。

書き順チェック、消しゴム、undo 機能などをサポートしています。
-->

---
transition: slide-up
---

<h1 class="text-7xl">全形式共通</h1>

<div class="grid grid-cols-3 gap-4 text-4xl mt-12">
  <ul class="grid">
    <li>マルバツ</li>
    <li>模範解答</li>
    <li>採点
    </li>
    <li>etc...</li>
  </ul>
  <img src="/scored-with-answer.png" alt="[採点後の模範解答の表示]" class="mx-auto col-span-2 screen-shot-embed" />
</div>

<!--
全形式共通の機能。

マルバツ、模範解答の表示、採点機能、などなど。
-->

---
transition: slide-left
---

<h1 class="text-7xl mb-16">他にも...</h1>

<ul class="space-y-8 text-5xl">
  <li>Hiragana (ひらがなのみ入力)</li>
  <li>SelfScoring (自己採点)</li>
  <li>Speak (音声入力)</li>
  <li>etc...</li>
</ul>

<!--
先ほどご紹介した3つの問題形式（Choice、Write、KanjiHiraganaHandWriting）以外にも、aim@ は様々な問題形式に対応しています。

その他の問題形式として：
- Hiragana: ひらがなのみ入力
- SelfScoring: 自己採点問題 - 生徒自身が模範解答と照らし合わせて採点
- Speak: スピーキング問題 - 音声入力により英語の発音練習などに対応
-->

---
layout: section
transition: slide-up
---

<h1 class="text-6xl">実際のコンテンツ開発とその課題</h1>

<!--
ここまでお見せした問題についても自社で開発していて、弊社のコンテンツ開発チームの方が作成しています。

aim@ のコンテンツ開発にはいくつかの課題がありました。
-->

---
transition: slide-up
---

<h1 v-click>元々の学習画面</h1>

<img src="/old-aim-at.png" alt="元々の学習画面" class="mx-auto screen-shot-embed" />

<p class="text-4xl" v-click>CSV + 問題画像</p>

<ul class="grid gap-4 text-4xl" v-click>
  <li>問題画像の拡大・縮小</li>
  <li>解答欄と問題文が離れている</li>
</ul>

<div class="overlay overlay-blur" v-click>
  <img src="/sp-csv.png" alt="スマホで見た CSV コンテンツ" class="mx-auto my-20 screen-shot-embed" />
</div>

<p v-click class="overlay text-7xl emoji">🥲</p>

<style scoped>
:is(h1, ul, p) {
  position: absolute;
  width: fit-content;
  z-index: 10;
  background-color: var(--vue-green);
  border-radius: 10px;
  padding: 10px;
}

h1 { top: 30px; left: 30px; }

ul { top:300px; right: 10px; }

p { top: 150px; right: 10px; }

p.emoji {
  top: 330px;
  left: 660px;
  z-index: 1000;
  height: 130px;
  width: 130px;
}

.overlay { img { height: 500px; } }
</style>

<!--
こちらも aim@ の学習画面です。
パッと見は教材としては良さそうですが、、、？

（クリック）

これが元々の学習画面です。
左にあるのは問題画像です。

（クリック)

問題文を PDF で作成して、それを画像化していました。

CSV + 問題画像で問題を作成していました。
問題文は PDF を画像化したもの。解答欄の情報は CSV で管理。画像は拡大・縮小のみ。
見てください、解答欄と問題文が完全に分離してるんです。

PC だとまだマシですけど...

（クリック）

見づらいですし解きづらいですね(泣)
-->

---

<img src="/csv-content.png" alt="CSV コンテンツ" class="mx-auto screen-shot-embed h-125" />

<div :class="$slidev.nav.clicks === 0 ? 'hidden' : 'overlay overlay-blur'">
  <div class="text-3xl bg-white/90 p-8 rounded-lg">
    <ul v-if="$slidev.nav.clicks === 1">
      <li>問題文中に出てくる解答欄に直接入力できない</li>
      <li>スマホで見ると問題も解答欄もどちらも狭い</li>
      <li>問題画像の読み込みが完了するまでコンテンツを利用できない</li>
    </ul>
    <ul v-if="$slidev.nav.clicks === 2">
      <li>CSV のバリデーションがめんどい</li>
      <li>コンテンツ作成時のプレビューが大変</li>
      <li>画像データなのでレスポンシブ対応が大変 <br />(画像の拡大縮小くらい)</li>
      <li>PDF は扱いたくない、、、</li>
    </ul>
  </div>
</div>

<div v-if="$slidev.nav.clicks === 3" class="overlay">
  <img
    src="/csv-question-data.png"
    alt="CSV の問題データ"
    class="screen-shot-embed"
  />
</div>

<div style="display: none;" v-click />
<div style="display: none;" v-click />
<div style="display: none;" v-click />

<style scoped>
.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.05);
  display: flex;
  justify-content: center;
  align-items: flex-start;
  z-index: 1000;

  > div {
    background: rgba(255, 255, 255, 0.9);
    padding: 2rem;
    border-radius: 0.5rem;
    width: 80%;
    margin-top: 20vh;
    overflow-y: auto;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);

    h2 {
      font-size: 1.5rem;
      margin-bottom: 1.5rem;
      color: #333;
    }

    ul {
      list-style-type: disc;
      padding-left: 1.5rem;
      margin-bottom: 1rem;

      ul {
        list-style-type: circle;
        margin-top: 0.5rem;
      }
    }

    li {
      margin-bottom: 0.5rem;
      line-height: 1.5;
    }
  }

  img { width: 94%; display: grid; align-self: center; }
}

.hidden { display: none; }
</style>

<!--
元々は CSV + 問題画像 で問題、コンテンツを作成していました。

（クリック）

まずユーザー視点。

問題文中に「（1）の答えは〜」って書いてあっても、その場所に入力できない。下の解答欄まで目線を移動しないといけない。

スマホだと問題も解答欄も狭かった。

画像だから読み込み終わるまでも使えない。

（クリック）

そして開発者視点。

CSV のバリデーションが大変です。

プレビュー機能も大変。

画像データだからレスポンシブ対応も大変。

PDF は扱いたくない。
-->

---
layout: section
transition: slide-up
---

<h1 class="text-8xl">DSL で立ち向かう</h1>

---
transition: slide-up
---

<h1>何でどうやってコンテンツを作る？(ベース)</h1>

<br />

<ul class="grid gap-8 text-6xl">
  <li>LaTeX？ <devicon-latex /></li>
  <li>HTML？ <logos-html5 /></li>
  <li>Markdown？ <logos-markdown /></li>
  <li>独自フォーマット？</li>
</ul>

<style scoped>
h1 { font-size: 46px; }
</style>

<!--
CSV 以外の選択肢を考えてみましょう、新しいコンテンツフォーマットを何にするか。
HTML？、Markdown？、LaTeX？、独自フォーマット？
-->

---
transition: slide-up
---

<h1 class="flex items-center gap-5 mb-0">LaTeX <devicon-latex text-7xl mt-2 /></h1>

<br />
<br />

<p class="text-6xl flex gap-2 items-center"><mdi-circle-outline class="text-green-500" />表現力</p>
<small class="ml-20">数式や図表の表現力が高い</small>

<br />
<br />

<p class="text-6xl flex gap-2 items-center"><mdi-triangle-outline class="text-blue-500" />Web との親和性</p>
<small class="ml-20">HTML に変換できるけど、、、</small>

<br />
<br />

<p class="text-6xl flex gap-2 items-center"><mdi-triangle-outline class="text-blue-500" />馴染みのない開発者も多少</p>
<small class="ml-20">開発者都合だけど、、、</small>

<!--
まず LaTeX。

表現力、特に数式の表現力はピカイチです。教材では数式めちゃくちゃ使うので、これは魅力的。

図表とか複雑なレイアウトもできる。印刷してもキレイ。

でも...Web との親和性がちょっと...

HTML に変換できるっちゃできるけど、完璧じゃない。

あと、開発者もそうだけど、コンテンツ開発チームの人たちが LaTeX 知ってるかっていうと...

数式は魅力的だけど、Web アプリのフォーマットとしては厳しいなと。

ちなみにぼくは大学の課題は Word でやってました。
-->

---
transition: slide-up
---

<h1>HTML <logos-html5 /> (+ CSS)</h1>

<br />
<br />

<p class="text-6xl flex gap-2 items-center"><mdi-circle-outline class="text-green-500" />Web での表現力</p>

<br />
<br />

<p class="text-6xl flex gap-2 items-center"><mdi-close class="text-red-500" />手書きが面倒</p>
<small class="ml-20">タグを全部書くのが大変</small><br />
<small class="ml-20">数式も MathML で書く、、、？</small>

<!--
次、HTML。

Web での表現力は当然最高です。だって Web の標準ですから。

手書きは大変ですよね。
数式も MathML でも書けますが、、、
-->

---
transition: slide-up
---

<h1>Markdown <logos-markdown /></h1>

<br />
<br />

<p class="text-6xl flex gap-2 items-center"><mdi-circle-outline class="text-green-500" />比較的書きやすい/読みやすい</p>

<br />
<br />

<p class="text-6xl flex gap-2 items-center"><mdi-circle-outline class="text-green-500" />拡張が容易</p>
<small class="ml-20">既存のプロセッサやプラグインが利用できる(markdown-it など)</small>

<!--
そして Markdown。

比較的書きやすいし、読みやすいですよね。

拡張も簡単。
パーサー、markdown-it とか使えばプラグインも使える。
-->

---
layout: center
transition: slide-left
---

<div class="grid gap-8 text-7xl">
  <p>HTML を書きたい！</p>
  <p>(手書きは大変)</p>
  <p>HTML を簡潔に書きたい！！</p>
  <p>基本的には Markdown で</p>
  <p>LaTeX などは局所的に</p>
</div>

---
layout: section
class: text-7xl
transition: view-transition
---

<br />

<h1 class="flex items-center justify-center gap-12">
  <span class="view-a">A</span><span class="view-c">C</span><span class="view-d">D</span><span class="view-l">L</span>
</h1>

<style scoped>
.view-a { view-transition-name: a; color: var(--aim-at-red) !important; }
.view-c { view-transition-name: c; color: var(--aim-at-red) !important; }
.view-d { view-transition-name: d; color: var(--aim-at-red) !important; }
.view-l { view-transition-name: l; color: var(--aim-at-red) !important; }
</style>

---
layout: center
class: text-center
transition: view-transition
---

<h1><span class="view-a">A</span>im@ <span class="view-c">C</span>ontents <span class="view-d">D</span>efinition <span class="view-l">L</span>anguage</h1>

<style scoped>
.view-a { view-transition-name: a; color: var(--aim-at-red); }
.view-c { view-transition-name: c; color: var(--aim-at-red); }
.view-d { view-transition-name: d; color: var(--aim-at-red); }
.view-l { view-transition-name: l; color: var(--aim-at-red); }
</style>

---
transition: slide-up
---

<h1>
  <span class="view-a">A</span>im@ 
  <span class="view-c">C</span>ontents 
  <span class="view-d">D</span>efinition 
  <span class="view-l">L</span>anguage
</h1>

<div class="grid gap-16">
  <h2 class="text-4xl grid items-center">
    Markdown 拡張した DSL <span class="text-2xl">
    (<span class="font-bold text-#2897c8">D</span>omain <span class="font-bold text-#2897c8">S</span>pecific <span class="font-bold text-#2897c8">L</span>anguage)</span>
  </h2>
  <div class="grid grid-cols-3 gap-24">
    <div>
      <ul class="grid gap-2 text-3xl">
        <li>KaTeX</li>
        <li>ルビ、画像、動画</li>
        <li>sanitize</li>
      </ul>
    </div>
    <div class="col-span-2">
      <ul class="grid gap-2 text-3xl">
        <li>塾固有のレイアウト</li>
        <li>専用のタグ</li>
        <li>問題ごとのメタ情報</li>
      </ul>
    </div>
  </div>
  <div v-click class="overlay overlay-white">
    <div>
      <p class="text-5xl text-center">
        <span>1 問の問題、ヒント、解説、メタ情報を</span><br />
        <span>1 つのファイルで記述できる</span>
      </p>
      <p class="text-3xl text-end mt-15 mr-5"><logos-vue text-3xl mr-2 />SFC...?</p>
    </div>
  </div>
</div>

<style scoped>
.view-a { view-transition-name: a; color: var(--aim-at-red); }
.view-c { view-transition-name: c; color: var(--aim-at-red); }
.view-d { view-transition-name: d; color: var(--aim-at-red); }
.view-l { view-transition-name: l; color: var(--aim-at-red); }

.overlay {
  p:first-child {
    margin-top: 100px;
    background-color: var(--slidev-theme-background);
    padding: 10px;
    border-radius: 10px;
    border: 2px solid var(--slidev-theme-text);
  }
}
</style>

<!--
ここからは、実際にメイツで使用しているDSLである「ACDL」についてご紹介します。

ACDLは「Aim@ Contents Definition Language」の略で、教材コンテンツを記述するためのMarkdownベースのDSLです。

このDSLには以下の特徴があります：

1. Markdownの拡張機能
   - KaTeXによる数式表現
   - ルビ（ふりがな）機能
   - 画像・動画の埋め込みサポート

2. 塾業界特有の機能
   - 塾固有のレイアウト
   - 専用タグ（<aim-question>、<aim-hint>、<aim-answer>）
   - 問題ごとのメタ情報管理

3. セキュリティと品質
   - XSS対策のためのsanitize処理
   - 安全な属性・タグのみを許可する厳格な制御

クリックすると表示される最後のメッセージにある「SFC」は、Vue.jsのSingle File Componentを意識した設計思想を示唆しています。
-->

---
transition: slide-up
---

<h1 class="text-4xl">ACDL 例</h1>

<div class="grid grid-cols-2 gap-2">

<!-- prettier-ignore -->
```markdown
<aim-question>
## 因数分解小テスト

### １. 因数分解しなさい

(1) $9x^2 - 16=$ <aim-input />
</aim-question>

<aim-meta>
配点: '0'
解説画像:
  - kaisetsu.png
問題種類*: その他
問題形式: 演習問題形式
...
</aim-meta>
```

```markdown
<aim-answer>
(1) $9x^2 - 16 = (3x + 4)(3x - 4)$

<aim-img
  filename="kaisetsu.png"
  width="600px"
/>
</aim-answer>

<aim-hint>
# ヒント

- ヒント 1
- ヒント 2
- ヒント 3

</aim-hint>
```

</div>

<style scoped>
:deep(.slidev-code) {
  code {
    font-size: 1.2rem;
    line-height: 1.3;
  }
}
</style>

<!--
# ACDL の例

こちらが ACDL の実際の記述例です。

左側に問題とメタ情報、右側に解答とヒントが記述されています。

- aim-question タグで問題文を記述
- aim-input タグで解答欄を配置
- aim-meta タグで配点や問題種別などのメタ情報を管理
- KaTeX で数式を表現

このように、一つのファイルで問題、解答、ヒント、メタ情報をすべて管理できます。
Vue の SFC のようなイメージですね。
-->

---

<img src="/cms-example.png" alt="aim@ CMS のサンプル" class="w-200 mx-auto screen-shot-embed" />

<!--
# ACDL コンテンツを管理する CMS

こちらは実際に ACDL で記述したコンテンツを管理する CMS の画面です。

CMS も自社で開発しています。

左側に ACDL のエディタ、右側にプレビューが表示されています。
コンテンツ開発者はリアルタイムでプレビューを確認しながら、問題を作成できます。

SFC のように単一のファイルになっていることで、CMS エディタを使わなくても手元のエディタでファイルを編集することも可能です。
CMS からダウンロードして、手元のエディタで修正してアップロードする、、、のように

これにより、CSV + 画像の時代と比べて、コンテンツ開発の DX が大幅に改善されました。
-->

---
layout: section
transition: slide-up
---

<h1 class="text-6xl">ACDL のランタイム</h1>

<!--
# ACDL のランタイム
-->

---
transition: slide-up
layout: center
---

<div class="grid grid-cols-2 gap-6">
  <div class="border border-gray-300 rounded-xl p-6 shadow-lg w-110">
    <h2 class="text-4xl font-bold mb-4">ユーザー入力</h2>
    <ul class="space-y-2 text-2xl">
      <li class="flex items-start">
        <span class="mr-2 mt-1">•</span>
        自作ソフトウェアキーボード
      </li>
      <li class="flex items-start">
        <span class="mr-2 mt-1">•</span>
        入力フィールドの状態管理
      </li>
      <li class="flex items-start">
        <span class="mr-2 mt-1">•</span>
        解答のバリデーション
      </li>
    </ul>
  </div>
  <div class="border border-gray-300 rounded-xl p-6 shadow-lg">
    <h2 class="text-4xl font-bold mb-4">メディアの取り扱い</h2>
    <ul class="space-y-2 text-2xl">
      <li class="flex items-start">
        <span class="mr-2 mt-1">•</span>
        ストリーミング
      </li>
      <li class="flex items-start">
        <span class="mr-2 mt-1">•</span>
        プレイヤー
      </li>
      <li class="flex items-start">
        <span class="mr-2 mt-1">•</span>
        認可
      </li>
      <li class="flex items-start">
        <span class="mr-2 mt-1">•</span>
        cleanup の処理
      </li>
    </ul>
  </div>
</div>

<!--
# DSL だけでは動かない

ACDL で記述しただけでは、まだインタラクティブな教材は完成しません。
実際に動作させるためには、様々な技術要素を実装する必要があります。

これは一般的なプログラミング言語でも同じです。
- 言語仕様（Language Specification） だけでは実行できない
- ランタイム（Runtime Environment） が必要
- インタープリタ/コンパイラ（Interpreter/Compiler） による変換
- 実行環境（Execution Environment） でのリソース管理

ACDL も同様に、DSL として以下が必要：
- パーサー（Parser）：ACDL を解析して AST に変換
- レンダラー（Renderer）：AST から HTML を生成
- ランタイムシステム（Runtime System）：インタラクティブ機能の実装

そしてここからが本題です。実際にインタラクティブな教材として動作させるために必要な技術要素を見てみましょう。

左側のボックス：ユーザー入力
- 自作ソフトウェアキーボード：数式入力、英語入力、手書き入力など、様々な入力方法に対応
- 入力フィールドの状態管理：フォーカス状態、入力値、バリデーション状態など
- 解答のバリデーション：数式の正しさ、文字数制限など

右側のボックス：メディアの取り扱い
- ストリーミング：動画や音声のストリーミング再生
- プレイヤー：再生・一時停止・シークなどの制御
- 認可：メディアファイルへのアクセス権限管理
- cleanup の処理：メモリリークを防ぐための適切なリソース管理

これらの複雑な機能を実装しつつ、先ほど話した「Vue と生 DOM の混在」「命令的な記述」「nextTick() 問題」といった課題を解決する必要があります。

実際の動作にはランタイム実装が不可欠で、これが今日のメインテーマです。
-->

---

<h1>インタラクション実装 (ランタイム) の課題</h1>

<br />

<div v-if="$slidev.nav.clicks === 0" class="text-4xl grid">
  <ul class="grid gap-10">
    <li>コンテンツは DSL で記述されて、生の HTML (DOM) <br />に変換される</li>
    <li><logos-vue /> で実装する部分と生 DOM を混ぜ合わせて<br />インタラクティブにする必要がある</li>
  </ul>
  <br />
  <span class="mb-4 text-3xl">例えば</span>
  <span class="text-2xl font-bold">ソフトウェアキーボード、採点処理時に正誤を表示、etc...</span>
</div>

<div v-if="$slidev.nav.clicks === 1" class="overlay overlay-white">
  <div>
    <ul class="text-4xl grid gap-6">
      <li>愚直にやると <logos-vue /> の世界と生 DOM の世界を<br />何度も行き来することになる</li>
      <li>
        生 DOM をいじると UI の記述が命令的になる
        <ul class="mt-6 text-3xl grid gap-4 list-disc px-10">
          <li>selector はどうするか</li>
          <li>その時点での DOM 全体の構造が不明</li>
          <li>イベントリスナーの管理がめんどくさい</li>
        </ul>
      </li>
    </ul>
    <p class="mt-12 font-bold text-4xl text-center">UI の仕様がわからなくなる (なんでもできてしまう)</p>
  </div>
</div>

<p v-if="$slidev.nav.clicks === 2" class="text-4xl leading-18">
  あらゆるところで <logos-vue /> のスケジューラーのことを考慮<br />しながら実装する必要がある
  <br />
  <span class="text-3xl">(どこで nextTick() を使うか使わないか)</span>
</p>

<template v-if="$slidev.nav.clicks === 3">
  <p class="text-4xl font-bold underline mt-4">これらをうまく解決したい</p>

  <ul class="text-5xl grid gap-10 mt-10">
    <li><logos-vue /> と生 DOM の組み合わせ</li>
    <li>生 DOM 操作の命令的な記述</li>
    <li><logos-vue /> のスケジューラー (nextTick())</li>
  </ul>
</template>

<div style="display: none;" v-click />
<div style="display: none;" v-click />
<div style="display: none;" v-click />

<style scoped>
h1 { font-size: 47px; }
</style>

<!--
DSL で作られた教材コンテンツは後で触れますが、静的な HTML に変換されます。
ただの静的な HTML として表示するだけでなく、インタラクティブにする必要があります。

DSL から生成された生の DOM と、Vue.js で実装するインタラクティブな機能を組み合わせる必要があるという話です。

ソフトウェアキーボードは、例えば数学の問題で数式を入力する際に、特殊な記号（分数、ルート、累乗など）を簡単に入力できるようにする仮想キーボードのことです。通常のキーボードでは入力しづらい数学記号を、画面上のボタンをクリックして入力できます。

(クリック)

Vue.js の仮想 DOM の世界と、DSL から生成された実際の DOM を行き来すると、どちらがどの部分を管理しているのか複雑になります。

生の DOM を直接操作すると：
- どの要素を選ぶか（querySelector など）を文字列で指定する必要がある
- DOM の構造が変わったときに壊れやすい
- イベントリスナーの登録・解除を手動で管理する必要がある
- コードを読んでも、どういう UI になるのか想像しづらい

(クリック)

Vue.js には内部的にスケジューラーがあり、DOM の更新タイミングを最適化しています。

nextTick() は、Vue が DOM を更新した後に実行したい処理を予約する関数です。Vue と生 DOM を混在させると、このタイミング制御が複雑になり、バグの原因になりやすいです。
「`nextTick()` を使わないと動かない」みたいなコメントが、、、
-->

---
transition: slide-up
---

<h1 class="text-6xl">ランタイムの実装のアプローチ</h1>

<p class="text-5xl mt-16">実装を 2 つの空間に分離する</p>

<div class="grid grid-cols-2 gap-8 mt-10">
  <div class="border p-8 border-solid border-gray-300 rounded-lg">
    <h2 class="text-6xl mb-4 font-bold">Infra</h2>
    <p class="text-4xl mt-8">UI 更新の仕組み</p>
  </div>
  <div class="border p-8 border-solid border-gray-300 rounded-lg">
    <h2 class="text-6xl mb-4 font-bold">Impl</h2>
    <p class="text-4xl mt-8">ビジネスロジック</p>
  </div>
</div>

<!--
Infra: Bridge を動くようにする、Bridge が更新されたらどう UI を更新するかについての実装
Impl: Bridge を使って UI に関するビジネスロジックをかく
-->

---

# Infra のアーキテクチャ

<img
  src="/aim-at-markdown-arch.png"
  alt="aim@ のアーキテクチャ"
  class="w-145 mx-auto"
/>

<p
  style="position: absolute; bottom: 345px; right: 520px;"
  class="text-4xl description"
  v-click
>
  宣言的な UI の状態
  <br />
  (デカい reactive object)
</p>

<p
  style="position: absolute; bottom: 130px; right: 100px;"
  class="text-4xl description"
  v-click
>
  ACDL → HTML
</p>

<p
  style="position: absolute; bottom: 235px; right: 20px;"
  class="text-4xl description"
  v-click
>
  HTML にインタラクティブな機能を注入
</p>

<style scoped>
.description {
  background-color: var(--slidev-theme-accent);
  color: var(--slidev-theme-background);
  padding: 10px 20px;
  border-radius: 10px;
  font-weight: bold;
}
</style>

<!--
それでは、Infra レイヤーのアーキテクチャを見ていきましょう。

この図は、aim@ のランタイムがどう動いているかを示したものです。
大きく3つのコンポーネントに分かれています。

（クリック）

Bridge。
これは巨大なリアクティブオブジェクトで、UI のすべての状態を管理しています。
選択肢の選択状態、入力値、フォーカス状態、採点結果など、あらゆる情報がここに集約されています。
Vue.js の ref() で作られているので、状態が変わると自動的に UI が更新されます。

（クリック）

Render。
ACDL で書かれたマークダウンを HTML に変換する役割です。
markdown-it をベースに、独自の拡張を加えて、aim-input タグなどを適切な HTML に変換します。

（クリック）

Hydration。
Render で生成された静的な HTML に、インタラクティブな機能を注入します。
イベントリスナーの設定、Bridge との接続、DOM 要素の参照保持などを行います。

それぞれ詳しく見ていきましょう。
-->

---

<h1 class="text-6xl">Render</h1>

<div class="grid grid-cols-3">
<div>

<ul class="grid gap-4 text-4xl">
  <li>ACDL → HTML</li>
  <br />
  <li>pre process</li>
  <li>post process</li>
  <li>sanitize</li>
</ul>

</div>
<div class="col-span-2">

<!-- prettier-ignore -->
```ts
function render(
  s: string,
  opts?: RenderOptions
): string {
  return [
    preProcess,
    markdown.render,
    postProcess,
    sanitize,
  ].reduce((acc, p) => p(acc, opts), s);
}

interface RenderOptions {
  shouldRenderMedia: boolean;
  isVertical: boolean;
  // etc...
}
```

</div>
</div>

<div
  v-if="$slidev.nav.clicks === 1"
  class="overlay overlay-blur"
  style="overflow: hidden; padding: 10px;"
>
<div class="w-200 relative">

<div class="absolute top-7 right-10 text-white bg-gray-800 px-2 py-1 rounded text-3xl font-bold z-10">ACDL</div>

<!-- prettier-ignore -->
```html
## 因数分解小テスト

### １. 因数分解しなさい

(1) $9x^2 - 16=$ <aim-input />
```

<div
  class="absolute top-7 right-10 text-white bg-gray-800 px-2 py-1 rounded text-3xl font-bold z-10"
  style="margin-top: 10rem;;"
>
  HTML
</div>

<br />

```html
<div class="pa-2 rendered overflow-y-auto full-height">
  <h2>因数分解小テスト</h2>
  <h3>１. 因数分解しなさい</h3>
  <p>
    (1)
    <span class="katex">
      <span class="katex-html">
        <span class="base">
          <span
            class="strut"
            style="height:0.897438em;vertical-align:-0.08333em;"
          ></span>
          <span class="mord">9</span>
          <span class="mord">
            <span class="mord mathnormal">x</span>
            <span class="msupsub">
              <span class="vlist-t">
                <span class="vlist-r">
                  <span class="vlist" style="height:0.8141079999999999em;">
                    <span style="top:-3.063em;margin-right:0.05em;">
                      <span class="pstrut" style="height:2.7em;"></span>
                      <span class="sizing reset-size6 size3 mtight">
                        <span class="mord mtight">2</span>
                      </span>
                    </span>
                  </span>
                </span>
              </span>
            </span>
          </span>
          <span
            class="mspace"
            style="margin-right:0.2222222222222222em;"
          ></span>
          <span class="mbin">−</span>
          <span
            class="mspace"
            style="margin-right:0.2222222222222222em;"
          ></span>
        </span>
        <span class="base">
          <span
            class="strut"
            style="height:0.64444em;vertical-align:0em;"
          ></span>
          <span class="mord">1</span>
          <span class="mord">6</span>
          <span
            class="mspace"
            style="margin-right:0.2777777777777778em;"
          ></span>
          <span class="mrel">=</span>
        </span>
      </span>
    </span>
    <span class="question-field">
      <span class="question-field-input-wrapper">
        <input class="question-field-input" data-aim-tag="" placeholder="" />
      </span>
      <span class="question-field-error"></span>
    </span>
  </p>
</div>
```

</div>
</div>

<div v-click style="display: none;" />

<style scoped>
.overlay {
  display: grid;
  justify-items: center;
}

:deep(.slidev-code) {
  code { font-size: 1.1rem; line-height: 1.2; }
}
</style>

<!--
Render についてです。

実は render と言いつつ、preProcess、postProcess、sanitize も含まれています。

RenderOptions で、縦書きモードやメディア表示の制御など、レンダリング時の設定を指定します。

（クリック）

実際の変換例はこんな感じです。
-->

---
transition: slide-up
---

<h1 class="text-5xl">Bridge</h1>

<div class="grid gap-8">
<ul class="grid gap-2">
  <li class="text-3xl">宣言的な UI の状態</li>
  <li class="text-3xl">問題データから作成されるリアクティブオブジェクト</li>
</ul>

<div>

<img src="/vue-bridge-dom.drawio.svg" alt="what is bridge?" class="w-170 mx-auto" />

</div>
</div>

<!--
Bridge について。

Bridge とはその名の通り、橋渡しの役割をもつオブジェクトです。

Vue と 実 DOM を繋ぐ役割を持っています。

宣言的な  UI の状態を表現しています。

問題データから取得される巨大なオブジェクト、リアクティブオブジェクトです。
-->

---
layout: center
transition: slide-up
---

<img src="/bridge-structure.drawio.svg" alt="what is bridge?" class="h-120 mx-auto" />

<div v-if="$slidev.nav.clicks === 1" class="overlay overlay-blur">
<div class="bg-white/90 p-8 rounded-lg">

```ts
const bridge = ref<MarkdownQuestionBridge | null>(null);

interface MarkdownQuestionBridge {
  questionFormatsBridges: QuestionFormatBridge[];
}

type QuestionFormatBridge =
  | SingleFormatBridge
  | SpeakFormatBridge
  | ChoiceFormatBridge
  | WriteFormatBridge
  | SelfScoringFormatBridge;
//  ...
```

</div>
</div>

<div v-click style="display: none;" />

<style scoped>
.overlay {
  > div {
    width: fit-content;
    display: grid;
    justify-self: center;
    place-items: center;
    height: 100%;

    :deep(.slidev-code) {
      code {
        font-size: 1.5rem;
        line-height: 1.3;
      }
    }
  }
}
</style>

<!--
Bridge の構造を図にするとこのようになります。

ユーザーからの入力を受け取るためのキーボードの情報を持ちます。

また、解答のの正誤情報も持ちます。

QuestionField とは HTMLInputElement とそのラッパーであり、入力された値や class 名のリストを持ちます。

(クリック)

コードで簡略的に表現するとこのようになります。
-->

---
transition: slide-left
---

<h1 class="text-5xl">Bridge は巨大リアクティブオブジェクト</h1>

<div class="grid gap-8 mt-12">
  <p class="text-5xl text-gray-600"><span v-mark="{ color: 'var(--aim-at-red)' }">すべての UI 状態を管理</span></p>

  <div class="mt-8">
    <p class="text-4xl flex items-center gap-2"><logos-vue /> の reactivity system が嬉しい</p>
    <div class="grid grid-cols-2 gap-8 mt-12">
      <div class="p-8 border bg-#42b883 rounded-lg text-center">
        <p class="text-4xl font-bold text-#35495e">.value</p>
      </div>
      <div class="p-8 border bg-#35495e rounded-lg text-center">
        <p class="text-4xl font-bold text-#42b883">deep watch</p>
      </div>
    </div>
  </div>
</div>

<style scoped>
.text-aim-at-red { color: var(--aim-at-red); }
</style>

<!--
# Bridge と Vue の相性

Bridge は巨大なリアクティブオブジェクトとして、すべての UI 状態を管理しています。

(クリック)

全ての UI の状態を管理、表現する単一のリアクティブオブジェクトです。

Vue の reactivity system と特に相性が良い点：

## .value インターフェース
```ts
bridge.value.questionFormatsBridges[0].values[0] = "新しい値"
// → 自動的に UI が更新される
```

深くネストしたプロパティへのアクセスでも、Vue の reactivity が追跡してくれるため、
値を変更するだけで自動的に UI が更新されます。

## deep watch
```ts
watch(bridge, () => {
  hydratedHandler?.update?.()
}, { deep: true })
```

`{ deep: true }` オプションにより、巨大なオブジェクト構造の中の
どこかが変更されても検知できます。

Vue の Proxy ベースの reactivity system は、
このような巨大なオブジェクト構造でも効率的に動作します。
-->

---
transition: slide-up
---

<h1 class="text-8xl">Hydration</h1>

<br />

<div class="grid grid-cols-2">

<ul class="grid gap-10 ">
  <li class="text-4xl">DOM と Bridge のリンク</li>
  <li class="text-3xl">Vue の世界の外で DOM 操作</li>
</ul>

```ts
hydrate({
  markdownQuestionBridge,
  inputElementClassName,
  // ...
});
```

</div>

<style scoped>
:deep(.slidev-code) {
  height: fit-content;
  code {
    font-size: 1.5rem;
    line-height: 1.3;
  }
}
</style>

<!--
SSR やってる人は聞き覚えがあるかもしれませんね。静的な HTML に動的な機能を注入するプロセスです。

Hydration の役割は2つ。

1つ目、DOM と Bridge のリンク。
Render で生成された HTML の DOM 要素を取得して、Bridge の状態と接続します。

2つ目、Vue の世界の外で DOM 操作。
ACDL から生成された DOM は Vue の管理外なので、イベントリスナーの設定とか、直接 DOM をいじる必要があるんです。

hydrate 関数に Bridge とセレクタ情報を渡すと、静的な HTML が動的になります。

SSR の Hydration と似てますけど、Vue の仮想 DOM じゃなくて、独自の Bridge を使ってるところが違います。
-->

---
transition: slide-up
---

<p class="text-5xl">{{ message }}</p>

<br />
<br />

````md magic-move
```ts
const real: document.getElementById(hydrationId);
```

```ts
ctx.markdownQuestionBridge.value?.questionFormatsBridges.forEach(
  (markdownQuestionFormat, i) => {
    switch (markdownQuestionFormat.type) {
      case QuestionFormatBridgeType.Write:
      case QuestionFormatBridgeType.Choice: {
        hydrateInput(ctx, real, markdownQuestionFormat, i);
        break;
      }
      // ...
    }
  }
);
```

```ts
function hydrate(ctx: HydrateContext): HydratedHandler {
  // ...
  const update = () => {
    try {
      internalUpdate(ctx, real);
    } catch (e) {
      // error handling
    }
  };

  // HydratedHandler
  return { update /* ... */ };
}
```
````

<script setup>
import { computed } from "vue";
const message = computed(() => {
  if ($slidev.nav.clicks === 0) return "1. 対象の DOM 要素を取得";
  if ($slidev.nav.clicks === 1) return "2. DOM に Bridge を hydrate ";
  if ($slidev.nav.clicks === 2) return "3. HydratedHandler の生成";
  return "";
});
</script>

<style scoped>
:deep(.slidev-code) {
  font-size: 1.4rem !important;
  line-height: 1.3 !important;
}
</style>

<!--
Hydration のプロセスは3ステップ。

1つ目、対象の DOM 要素を取得。
querySelector で ACDL から生成された解答欄を全部取ってきます。

2つ目、DOM に Bridge を hydrate。
Bridge の各 QuestionFormat に対応する DOM 要素を見つけて、hydrateInput を実行。これで DOM と Bridge の状態がつながります。

3つ目、HydratedHandler の生成。
update 関数を返します。Bridge の状態が変わったときに、この update を呼ぶと DOM が更新される仕組み。

「これって SSR の Hydration と同じ？」ってよく聞かれるんですけど、概念は似てます。でも Vue の仮想 DOM じゃなくて独自の Bridge を使ってるところが違います。
-->

---

<!-- prettier-ignore -->
```ts
// bridge を生成
bridge.value = build(questionFormats, /* ... */);

// DOM を生成 (v-html で挿入)
renderedQuestionText.value = render(acdl, /* ... */);

// bridge を DOM に hydrate
nextTick(() => {
  hydratedHandler = hydrate({
    markdownQuestionBridge: bridge,
    targetSelector: "#question-42445345736", 
    /* ... */
  });
});
```

<br />

<!-- prettier-ignore -->
```ts
// Bridge を watch して受け取った HydratedHandler を実行することで UI を更新する
const bridge = ref<MarkdownQuestionBridge | null>(null);
watch([bridge, activeQuestionFieldInfo], () => hydratedHandler?.update?.(), 
  { deep: true },
);
```

<div v-if="$slidev.nav.clicks === 1" class="overlay">

<img
  src="/aim-at-markdown-arch.png"
  alt="aim@ のアーキテクチャ"
  class="mx-auto h-130"
/>

</div>

<div v-click style="display: none;" />

<style scoped>
h1 {
  font-size: 4rem;
  position: absolute;
  top: 10px;
  right: 10px;
  z-index: 999;
  border: 1px solid var(--slidev-theme-text);
  padding: 1px;
  border-radius: 10px;
}


:deep(.slidev-code) {
  code {
    font-size: 1.1rem;
    line-height: 1.3;
  }
}
</style>

<!--
実際のコードでどう実装してるか見てみましょう。

まず Bridge を生成。
```ts
bridge.value = build(questionFormats, /* ... */);
```
問題データから巨大なリアクティブオブジェクトを作ります。

次に HTML を生成。
```ts
renderedQuestionText.value = render(markdown, /* ... */);
```
ACDL を HTML に変換。これを v-html で DOM に突っ込みます。

そして Hydration。
```ts
nextTick(() => {
  hydratedHandler = hydrate({ /* ... */ });
});
```
nextTick 重要です！DOM のレンダリングを待たないと、hydrate が空振りします。

最後に自動更新の設定。
```ts
watch([bridge, activeQuestionFieldInfo], () => hydratedHandler?.update?.(), 
  { deep: true },
);
```
deep: true で Bridge の中身まで全部監視。変更があったら update を呼ぶ。

（クリック）

この図を見ると、全体の流れがわかりやすいですね。Bridge が中心にあって、Render と Hydration がそれを DOM につなげている。

これで ACDL のコンテンツが Vue.js のリアクティビティを活かした教材になるんです。
-->

---

<h1 class="text-7xl">ここまでで Infra は揃った</h1>

<br />

<p class="text-6xl leading-18">Bridge を操作することで<br />UI が更新される</p><br />
<p class="text-6xl leading-18">Bridge を使って UI に関する<br />ビジネスロジックを実装していく</p>

<!--
ここまでで Infra は揃いました。

Bridge、Render、Hydration。この3つで基盤ができました。

Bridge を操作すれば UI が更新される。Vue の reactivity のおかげで自動的に。

生 DOM と Vue の世界もつながった。

じゃあ次は、この基盤の上にビジネスロジックを乗せていきます。それが Impl レイヤーです。
-->

---

<h1 class="text-5xl">Impl</h1>

<div class="grid gap-8">
  <p class="text-4xl">Bridge を使って UI に関するビジネスロジックを記述</p>

  <ul class="grid gap-4 text-3xl">
    <li>時間切れ → 自動採点 → <mdi-circle-outline class="text-green-500" /><mdi-close class="text-red-500" /></li>
    <li>学習フェーズ (回答中、採点後、見直し) の変更 → UI の更新</li>
    <li>選択肢選択のビジネスロジック <span class="text-xl">(コンテンツの設定によって挙動が変わる)</span>
      <ul class="mt-3 text-xl list-disc ml-6">
        <li :class="$slidev.nav.clicks === 1 ? 'text-aim-at-red' : ''">選択済み選択肢 (追加されるのか、解除されるのか)</li>
      </ul>
    </li>
    <li>数式入力の不正な入力に対するバリデーション
      <ul class="mt-3 text-xl list-disc ml-6">
        <li>累乗のネストや 2 重根号、半分数の禁止、etc...</li>
      </ul>
    </li>
    <li>
      <span :class="$slidev.nav.clicks === 1 ? 'text-aim-at-red' : ''">左右キーの押下で解答欄移動</span>、etc...
    </li>
  </ul>

  <div v-if="$slidev.nav.clicks === 1" class="overlay overlay-blur">
    <p class="text-4xl leading-relaxed px-8">
      中でも DSL によってレンダリングされた部分からの<br />イベント (input, focus, blur, etc...) は <span class="text-aim-at-red">UserAction</span> <br />という名前で実装されている
    </p>
  </div>
</div>

<!--
Impl レイヤーでは、Bridge を使って教材のビジネスロジックを実装します。

例えばこんなの。

時間切れになったら自動採点。タイマーが0になったら、Bridge の状態を変えて、マルバツを表示。

学習フェーズの管理。回答中、採点後、見直し。それぞれで UI の振る舞いが違う。

（クリック）

選択肢選択のロジック。これが結構複雑で、単一選択なのか複数選択なのか、すでに選択済みだったら解除するのか追加するのか...

数式入力のバリデーション。2の2の2乗みたいな累乗のネストはダメとか、二重根号はダメとか。数学的におかしいものを弾く。

左右キーで解答欄移動。これ地味に便利。

（クリック）

これらのイベント処理を UserAction という概念でまとめています。DSL でレンダリングされた要素からのイベントを、きれいに処理できるようにしました。
-->

<div v-click style="display: none;" />

<style scoped>
.overlay {
  z-index: 999;
  padding: 2rem;

  > p {
    margin-bottom: 250px;
    padding: 1rem;
    border-radius: 1rem;
    background-color: var(--slidev-theme-background);
    height: fit-content;
    border: 2px solid var(--slidev-theme-text);
  }
}

.overlay-blur { backdrop-filter: blur(1px); }

.text-aim-at-red { color: var(--aim-at-red); }
</style>

---

<h1 class="text-4xl">キーボードごとに多様なアクションが実装</h1>

<br />
<br />
<br />

<img v-if="$slidev.nav.clicks === 0" src="/keyboard-math.png" alt="" class="w-full mx-auto screen-shot-embed" />
<img v-if="$slidev.nav.clicks === 1" src="/keyboard-choice.png" alt="" class="w-full mx-auto screen-shot-embed" />
<img v-if="$slidev.nav.clicks === 2" src="/keyboard-chemistry.png" alt="" class="w-full mx-auto screen-shot-embed" />
<img v-if="$slidev.nav.clicks === 3" src="/keyboard-tegaki.png" alt="" class="w-full mx-auto screen-shot-embed" />

<div v-if="$slidev.nav.clicks === 4" class="mt-4">
    <h2 class="text-3xl font-semibold mb-10">実 DOM にバインドされる UserActions</h2>
    <ul class="list-disc list-inside space-y-6 text-2xl">
      <li>handleInput</li>
      <li>handleFocus</li>
      <li>handleBlur</li>
      <li>handleClickDeleteButton</li>
    </ul>
    <img src="/hydration-binding-user-actions.png" alt="" class="h-110 mx-auto screen-shot-embed absolute bottom-5 right-30" />
</div>

<img v-if="$slidev.nav.clicks === 5" src="/user-actions.png" alt="" class="w-full mx-auto screen-shot-embed" />

<div v-click style="display: none;" />
<div v-click style="display: none;" />
<div v-click style="display: none;" />
<div v-click style="display: none;" />
<div v-click style="display: none;" />

<!--
キーボードごとに多様なアクションが実装されています。

（クリック）

数式キーボード。

（クリック）

選択肢キーボード。

（クリック）

化学式キーボード。

（クリック）

手書きキーボード。

（クリック）

これらのキーボードが発生させるアクションを実DOMにバインドする仕組みがあります。
handleInputで入力値の変更、handleFocusでフォーカス時の処理、handleBlurでフォーカス解除、handleClickDeleteButtonで削除処理。

重要な点：キーボードの種類によって発生するアクションは異なります。
例えば、選択肢キーボードには「全選択解除」、日本語キーボードにはinput/focus/blurなど、それぞれ特有のアクションがあります。

（クリック）

UserActionsの全体像です。
これはユーザーが行うアクション（入力、選択、削除など）を扱う概念で、Bridgeの世界観の範囲内です。
採点や中断などのアプリケーションロジックは含みません。
-->

---
transition: slide-up
---

<h1 class="text-6xl">binding</h1>

<p class="text-4xl">キーボードごとのアクションを DOM に紐付ける</p>

<br />
<br />
<br />

  <div class="grid gap-16 ">
    <ul class="text-4xl grid gap-8">
      <li><logos-vue /> コンポーネント (キーボード等) のイベント</li>
      <li>生 DOM (DSL でレンダリングされた要素) のイベント</li>
    </ul>
    <p class="text-4xl">異なる世界のイベントを統一的に扱いたい</p>
  </div>

<!--
でも、ここで課題があります。

2つの異なる世界のイベントを扱わないといけないんです。

1つ目、Vue コンポーネントのイベント。ソフトウェアキーボードとか、Vue で作ったやつ。@click とか普通に使える。

2つ目、生 DOM のイベント。ACDL からレンダリングされた解答欄とか。Vue の管理外。

でも、両方のイベントを同じように扱いたい。Bridge を通じて状態管理したい。

そこで、2つのバインディング方法を用意しました。
-->

---
transition: slide-up
---

<h1 class="text-6xl">2 つのバインディング方法</h1>

<h2 class="text-3xl">bind via <logos-vue text-2xl /> template</h2>

```html
<template>
  <EnglishKeyboard
    @click:english-key="bridge.userActions.english.vueBindings.swKeyboard.handleClickKey"
    ...
  />
</template>
```

<br />

<h2 class="text-3xl">bind via hydration</h2>

```ts
const hydrate = (/** ... */) => {
  // ...
  target.addEventListener("input", (e) =>
    bridge.userActions.english.hydrationBindings.handleInput(e)
  );
};
```

<div v-if="$slidev.nav.clicks === 1" class="overlay overlay-blur">
  <img src="/binding-methods.png" alt="user action binding" class="h-100 mx-auto mt-20" />
</div>

<div v-click style="display: none;" />

<style scoped>
ol { font-size: 1.4rem; }

:deep(.slidev-code) {
  code {
    font-size: 1.1rem;
    line-height: 1.1;
  }
}
</style>

<!--
2つのバインディング方法を紹介します。

1つ目、bind via Vue template。
Vue コンポーネントのイベントは、普通に Vue のテンプレートでバインド。
@click:english-key みたいなカスタムイベントで、Bridge の UserAction メソッドを直接呼び出す。
Vue の世界で完結。

2つ目、bind via hydration。
生 DOM のイベントは hydration のときにバインド。
addEventListener で直接イベントリスナーを設定。input、focus、blur とか標準の DOM イベント。
Vue の外側で起こるイベントの処理。

（クリック）

この図を見てください。両方のバインディングが Bridge の UserAction に集まってます。

イベントがどこから来ても、同じように処理できる。Vue コンポーネントだろうが生 DOM だろうが、UserAction として統一的に扱える。

これが設計のポイントです。
-->

---
layout: center
---

<img src="/cohesion.png" alt="VS Code でのディレクトリツリー" class="h-130 mx-auto" />

<style scoped>
.slidev-layout { background-color: #1E1F30 !important; }
</style>

<!--
実際のディレクトリ構造を見てみましょう。

各キーボードごとにフォルダが分かれていて、その中に
- bridge/：Bridge の定義
- hydration/：DOM へのバインディング
- userActions/：ビジネスロジック
- components/：Vue コンポーネント

がまとまってます。

これ、すごく良い構造で、各キーボードの実装が1箇所に集まってる。Infra と Impl の分離も明確。

新しいキーボード追加するときも、このパターンに従えばいいだけ。

凝集度が高いので、「数式キーボードのバグ直したい」ってなったら、そのフォルダだけ見ればいい。めちゃくちゃメンテしやすいです。
-->

---

<br />
<div class="grid gap-12 grid-cols-2">
  <div>
    <h2 class="text-6xl mb-8">Infra</h2>
    <ul class="grid text-4xl gap-4">
      <li>Bridge: UI の状態管理</li>
      <li>Render: ACDL → HTML</li>
      <li>Hydration: DOM 連携</li>
    </ul>
  </div>
  <div>
    <h2 class="text-6xl mb-8">Impl</h2>
    <ul class="grid text-4xl gap-4">
      <li>ビジネスロジック</li>
      <li>ユーザーアクション</li>
      <li>Bridge を操作して UI 更新</li>
    </ul>
  </div>
</div>

<ul class="text-4xl tracking-wider mt-24 grid gap-4">
  <li><span v-mark="{ color: 'var(--aim-at-red)' }">生 DOM と Vue の境界を明確にした</span></li>
  <li><span v-mark="{ color: 'var(--aim-at-red)' }">Bridge を操作して UI を更新 (UI を宣言的に記述)</span></li>
</ul>

<!--
ここまでのアーキテクチャをまとめます。

Infra（基盤）
- Bridge：巨大なリアクティブオブジェクトで UI 状態を全部管理
- Render：ACDL を HTML に変換
- Hydration：静的な DOM に動的機能を注入

Impl（実装）
- ビジネスロジック：教材特有の振る舞い
- ユーザーアクション：キーボードやマウスイベント
- Bridge 操作：状態変更で UI 更新

重要なポイントは2つ。

1つ目、生 DOM と Vue の境界を明確にした。
ACDL でレンダリングされた部分は生 DOM、キーボードとかは Vue コンポーネント。Bridge が橋渡し。

2つ目、Bridge を操作して UI を更新。
命令的な DOM 操作じゃなくて、宣言的。Vue の reactivity を最大限活用。

この設計のおかげで、あんなに複雑な教材インタラクションも、なんとか管理できるようになりました。
-->

---
layout: section
transition: slide-up
---

<h1 class="text-5xl">DSL でインタラクティブ教材に立ち向かう</h1>

<!--
ということで、DSL でインタラクティブ教材に立ち向かった話のまとめです。
-->

---

# まとめ

<div class="grid gap-16 text-5xl">
  <div class="before-after-container">
    <div class="image-wrapper">
      <img src="/choice-format-old.png" alt="Before: CSV + 画像形式" :class="$slidev.nav.clicks <= 1 ? 'active' : 'inactive'" />
      <div class="image-label" :class="$slidev.nav.clicks === 0 ? 'visible' : 'hidden'">Before (CSV + 画像)</div>
    </div>
    <div class="image-wrapper">
      <img src="/choice-format.png" alt="After: ACDL形式" :class="$slidev.nav.clicks <= 1 ? 'inactive' : 'active'" />
      <div class="image-label" :class="$slidev.nav.clicks === 0 ? 'hidden' : 'visible'">After (ACDL)</div>
    </div>
  </div>

  <div v-click style="display: none;" />

  <div class="overlay overlay-white" v-if="$slidev.nav.clicks === 1">
    <div>
      <ul class="grid gap-4">
        <li>CSV + 画像では解答欄と問題文が分離</li>
        <li>レスポンシブ対応の困難さ</li>
        <li>インタラクティブな教材実装の複雑性</li>
      </ul>
    </div>
  </div>

  <div v-click style="display: none;" />

  <div class="overlay overlay-white" v-click>
    <div>
      <ul class="grid gap-4">
        <li>問題文中に直接解答欄を配置</li>
        <li>マルチデバイス対応の実現</li>
        <li>コンテンツ開発の DX 改善</li>
        <li class="text-3xl">(単一ファイル、 プレビュー環境)</li>
      </ul>
    </div>
  </div>

  <div class="overlay overlay-white" v-click>
    <div>
      <ul class="grid gap-4">
        <li>ACDL (DSL) によるコンテンツ記述</li>
        <li>Bridge による宣言的な UI 記述</li>
        <li>ドメインロジックの凝集度の向上</li>
      </ul>
    </div>
  </div>
</div>

<style scoped>
.before-after-container {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 2rem;
  width: 100%;
  margin: 0 auto 2rem;
  height: 400px;
}

.image-wrapper {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

.image-wrapper img {
  height: 300px;
  width: auto;
  transition: all 0.6s ease-in-out;
  border-radius: 0.5rem;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
}

.image-wrapper img.active {
  height: 380px;
  filter: brightness(1);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.image-wrapper img.inactive {
  height: 150px;
  filter: brightness(0.3) opacity(0.5);
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
}

.image-label {
  color: var(--slidev-theme-text);
  font-size: 1.5rem;
  font-weight: 600;
  transition: opacity 0.6s ease;
  margin-top: 0.5rem;
}

.image-label.visible {
  opacity: 1;
}

.image-label.hidden {
  opacity: 0.3;
}

</style>

<!--
Before と After を見比べてみましょう。

（アニメーション）

Before。CSV + 画像。問題文と解答欄がバラバラ。スマホだと使い物にならない。

After。ACDL。問題文中に解答欄を直接配置できる。レスポンシブ対応もバッチリ。

（クリック）

従来の課題。CSV + 画像では解答欄と問題文が分離。レスポンシブ対応？何それ？インタラクティブな教材？無理無理。

（クリック）

DSL による解決。問題文中に直接解答欄を配置。マルチデバイス対応もできた。コンテンツ開発の DX も大幅改善。

（クリック）

技術的アプローチ。ACDL で記述、Bridge で宣言的に UI を管理、ドメインロジックもきれいにまとまった。

Vue.js のリアクティビティシステムと DSL の組み合わせ、これが効いたんです。複雑な教材インタラクションも、効率的に実装できるようになりました。
-->

---
layout: center
transition: slide-up
---

<h1 class="text-6xl">今後の課題</h1>

<div class="grid gap-8">
  <div>
    <h2 class="text-4xl mb-2 font-bold">レガシー CSV コンテンツの負債</h2>
    <ul class="grid gap-2 text-3xl ml-9 list-disc">
      <li>膨大なフォーマット、複雑怪奇な実装...</li>
      <li>ACDL 実装との二重管理</li>
    </ul>
  </div>

  <div>
    <h2 class="text-4xl mb-2 font-bold">テストと品質保証</h2>
    <ul class="grid gap-2 text-3xl ml-9 list-disc">
      <li>要件が複雑すぎて、動作確認が非常に大変</li>
      <li>テストの拡充と改善</li>
    </ul>
  </div>

  <div>
    <h2 class="text-4xl mb-2 font-bold">ACDL 自身の進化</h2>
    <ul class="grid gap-2 text-3xl ml-9 list-disc">
      <li>より表現力豊かに、より使いやすく</li>
    </ul>
  </div>
</div>

<!--
でも、まだ課題はあります。正直に言います。

レガシー CSV コンテンツの負債。
もう何万問って CSV 形式のコンテンツがあるんです。フォーマットも色々、実装も複雑怪奇。ACDL に移行したいけど、CSV もサポートしないといけない。二重管理が大変。

テストと品質保証。
要件が複雑すぎて、全パターンのテストなんて無理。問題形式×学習形式×デバイス×設定...組み合わせ爆発です。もっと効率的なテスト戦略が必要。

ACDL 自身の進化。
もっと表現力豊かにしたい。コンテンツ作成者にとってもっと使いやすくしたい。新しい問題形式にも対応したい。

これらの課題、まだまだ取り組んでいる最中です。
-->

---

<h1 class="text-7xl">Time is up...</h1>

<ul class="text-4xl grid gap-4 mx-16">
  <li v-click>タイマー</li>
  <li>
    <span class="block mb-3" v-click>生徒の学習フェーズ</span>
    <ul class="ml-8 mt-2 text-3xl list-disc grid">
      <li v-after>解答中</li>
      <li v-after>マルバツ</li>
      <li v-after>やり直し</li>
      <li v-after>etc...</li>
    </ul>
  </li>
  <li v-click>発音問題</li>
  <li v-after>etc...</li>
</ul>

<div v-click class="overlay overlay-white">
  <p class="text-4xl">But!!!!!!</p>
</div>

<div v-click class="overlay overlay-white">
  <div class="grid grid-cols-2 items-center mx-16">
    <p class="text-5xl">
      tech-lead of <img src="/mates-logo.png" alt="aim@" class="h-12 inline-block mx-2 mb-4" /><br />
      is here today ...lol<br/>
      <span class="text-2xl">(Ask him anything!)</span>
    </p>
    <img src="/ubugeeei-icon.jpg" alt="aim@" class="h-100" />
  </div>
</div>

<style scoped>
</style>

<!--
あー、もう時間がない...

まだまだ話したい機能があったんですよ。

（クリック）

タイマー機能。制限時間付きテストとか。

（クリック）

学習フェーズ管理。解答中、マルバツ表示、やり直し...それぞれで UI の振る舞いが違うんです。

（クリック）

発音問題！音声認識使った英語の発音練習。これも Vue で実装してて...

（クリック）

他にも...

（クリック）

But!!!!!

（クリック）

でも大丈夫です！実は aim@ のテックリードが今日ここに来てるんです！

彼は @ubugeeei として活動してて、Vue.js コミュニティでも有名な方です。chibivue の作者でもあります。

質問があったら、ぜひ彼に聞いてください！私が話せなかった技術的な詳細とか、面白い実装の話とか、たくさん持ってるはずです。

懇親会でも捕まえてください（笑）
-->

---
layout: center
class: text-center
---

<h1 class="text-5xl">仲間を募集しています</h1>

<div class="mt-12 grid grid-cols-2 gap-8">
  <div class="flex flex-col items-center">
    <img src="/wantedly.png" alt="Wantedly 上のメイツのページ" class="h-60 screen-shot-embed mb-4" />
    <p class="text-3xl text-center">Wantedly で<br />「メイツ」と検索！</p>
  </div>
  <div class="flex flex-col items-center">
    <img src="/vue-fes-japan-2025.png" alt="Vue Fes Japan 2025" class="h-60 screen-shot-embed mb-4" />
    <p class="text-3xl text-center">Vue Fes Japan<br />スポンサー (予定)</p>
  </div>
</div>

<!--
最後に宣伝です！

株式会社メイツでは、一緒に教育の未来を作る仲間を募集しています！

Wantedly で「メイツ」って検索してください。フロントエンドエンジニア、バックエンドエンジニア、フルスタックエンジニア、みんな募集中です。

カジュアル面談もやってるので、気軽に話を聞きに来てください。「v-tokyo から来た！」って言ってもらえると、効果測定ができて嬉しいです（笑）

あと、Vue Fes Japan 2025 のスポンサーもしています！Vue.js コミュニティへの貢献も積極的にやってます。

今日の話を聞いて「面白そう！」って思った方、ぜひお声がけください！懇親会でも待ってます！
-->

---
layout: section
class: text-3xl
---

# ありがとうございました
