# W3C勧告文書の日本語翻訳物作成手順 (案)

W3C勧告文書の日本語翻訳物作成手順の案について以下に示す．

## 1. 作業用ファイルフォーマットおよび管理方法に関する要件

### 1.1 作業用ファイルフォーマットに関する要件

作業用ファイルフォーマットとしては，W3C翻訳ガイドライン [1] に則り，HTMLを用いることが望ましい．

**※注意:** 最終的な公開物が，「印刷物で公開する」等の理由によりHTML以外のフォーマットである場合も，翻訳および査読作業はHTMLを用いて行い，最終的に公開する際に他のフォーマット (Word，PDF等) に変換することが望ましい．なお，他のフォーマットを用いる場合においても，図やリンク等，HTMLに含まれる情報を保存することが望ましい．

### 1.2 管理方法に関する要件

査読作業を確実に進めるため，査読対象ファイルのバージョンを確実に管理することが必要である．また，作業の効率化を図るために，査読対象ファイルを分散管理することが望ましい．

## 2. 具体的な作業の手順

### 工程1: 日本語原本の作成

上記「1.1 作業用ファイルフォーマットに関する要件」を考慮した上で，翻訳対象であるW3C仕様書 (英語原本) を日本語に翻訳し，「日本語原本」を作成する．

* 作業担当者: 事務局
* 工程生産物: W3C仕様書の日本語翻訳物 (日本語原本)
  * WoT Architecture: [作業用リポジトリ](https://github.com/wot-jp-community/wot-architecture) / [HTML](https://wot-jp-community.github.io/wot-architecture/index.html)
  * WoT Thing Description: TBD

### 工程2: 日本語原本の査読

まず，各査読単位を査読担者に割り当てた上で，以下の観点にもとづいて，各査読担当者が，各自の担当する査読単位の査読を行う．その結果にもとづいて，査読者全体で，やはり以下の観点にもとづいて，各査読担当者の査読結果を検証する．

**査読の観点:**

下記の工程2.2および工程2.3における査読作業にあたっては，以下の観点に留意する:
* 英語原本のスタイルが保存されているか (仕様書タイトル，各種リンク，著作権表示，章立て，図，文献等)
* 英語原本の文意が保存されているか
* 用語や言い回しが統一されているか
* 日本語として正しいか
* 誤字や脱字はないか

なお，工程2.2および工程2.3における査読作業にあたっては，英語原本中の文章の意味を変えないよう，できるだけ原文に忠実な翻訳となるように努める必要がある．一方，英語原文の意味がわかりづらいく，読者の理解を助けるために補足が必要な場合は，その補足部分について「訳者注釈」として明記する．

※訳者注のHTMLテンプレート
~~~
<div class="note" id="issue-container-generatedID">
<div role="heading" class="ednote-title marker" id="h-ednote" aria-level="5"><span>翻訳者のメモ</span></div>
<p>訳者注の記述内容をここに書きます。<br/>
訳者注の中で、文書中の他の箇所を引用する場合、以下の形式で章番号を参照してください。<a href="#sec-hypermedia-controls">§&nbsp;<bdi class="secno" >章番号.節番号.項番号</bdi> 章タイトル</a>。<br/>
また、引用内容は、以下のように <blocquote>〜</blockquote> を利用して引用してください。<br/>
<blockquote>引用内容をここに書きます。</blockquote>
</p>
</div>
~~~

### 工程2.1: 査読者の割当

査読担当者に過度な負担を強いない形で作業を円滑に進めるため，査読作業にあたっては，「日本語原本」を段落ごとに分けた上で特定の担当者に割り当てる．その際，各担当者の持つ知識および興味を考慮した上で割当を行う．

なお，段落ごとに分割した各担当者の査読対象部分を「査読単位」と呼ぶ．また，ある特定の査読単位の査読担当となった査読者のことを，その査読単位の「査読担当」と呼ぶ．

* 作業担当者: 査読者全員
* 工程生産物: どの査読担当が，どの査読単位を担当するかの対応関係 (査読割当表)

### 工程2.2: 各査読担当による査読

各査読担当は，割当表にもとづいて，各自が担当する査読単位の査読を行う．

なお，査読作業の結果，修正が必要と思われる場合，査読担当は，GitHubのPullrequestの仕組みを使って修正内容を提案する．なお，修正が必要だが，具体的な修正内容が不明な場合は，GitHubのIssueの仕組みを使い問題点の指摘を行う．

1. まずはGitHubのIssueを作る: https://github.com/wot-jp-community/wot-architecture/issues
1. 可能であれば，次にGitHubのPullrequestを作る
    1. まずHTMLの修正案を作る: https://github.com/wot-jp-community/wot-architecture/blob/master/index.html
    1. 次にPullrequestを作る: https://github.com/wot-jp-community/wot-architecture/pulls

なお，査読にあたっては[W3C仕様書の日本語翻訳にあたってのガイドライン (案)](https://github.com/wot-jp-community/wot-downstream-private/blob/master/meetings/20200730/rules.md)もご参照のこと．

作業担当者: 査読担当
工程生産物: GitHub上のPullrequest (もしくはIssue)

### 工程2.3: DSTF会合での検証

DSTF会合の中で，各査読担当が作成したPullrequestにもとづいて，GitHubのPR Preview機能を援用しながら，「対応する英語原本」と突き合わせながら，各査読単位の妥当性を検証する．

なお，工程2.2における各査読担当の査読結果として，「問題点があると思われるが，具体的な修正内容が不明」な場合は，その問題点について，GitHubのIssueとして指摘されているため，全体会合の中で具体的な修正内容について協議する．

* 作業担当者: 査読者全員
* 工程生産物: 修正版の査読単位

### 工程3: 最終翻訳結果確定

#### 工程3.1: 公開向けフォーマットに変換 (Optional)

工程2.3で生産した，修正版の査読単位から構成される，修正済みの日本語原本を，公開向けフォーマットに合わせて変換する(例えば，HTMLからPDFやWordへ変換する)．

* 作業担当者: 査読者有志および事務局
* 工程生産物: 問題点を修正の上，公開向けフォーマットに変換された日本語原本 (公開原本)

例)
* [Thing Descriptionの公開原本 (PDF)](https://github.com/wot-jp-community/wot-downstream/blob/master/wot-thing-description/Overview.pdf)
* [Thing Descriptionの公開原本 (Word)](https://github.com/wot-jp-community/wot-downstream/blob/master/wot-thing-description/Overview.docx)

#### 工程3.2: 最終確認

なお，公開に先立って，「公開原本」の内容について，あらためて「工程2: 日本語原稿の査読」の「査読の観点」に示すような観点での確認を行うべきであると考えられる．この最終確認作業については，「いつ・誰が行うか」を，公開先・査読者全員・事務局の間で意識合わせの上で，最終的な公開内容に問題のないようにする．

* 作業担当者: 査読担当者全員，事務局および公開先団体
* 工程生産物: 問題点がないことが確認された日本語原稿 (公開物)

文献:
[1] https://www.w3.org/Consortium/Translation/

以上
