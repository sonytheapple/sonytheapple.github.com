---
layout: post
title:  "당신의 전화번호를 알아맞히겠습니다"
date:   2016-03-15
excerpt: "니놈의 전화번호를 관신법으로 맞히겠다"
tag:
- markdown 
- syntax
- sample
- test
- jekyll
comments: true
---

## HTML Elements

Below is just about everything you'll need to style in the theme. Check the source code to see the many embedded elements within paragraphs.

# 당신은 과연 당신의 전화번호를 숨길 수 있다고 생각하세요?

# 저에겐 숨길수 없답니다^^

## 자 일단 계산기를 먼저 준비하세요

## 당신의 전화번호의 앞자리(예를들어 전화번호가 010-1234-5678이라면 1234)를 250에 곱해주세요

## 그다음에 다시 80을 곱해주세요

## 그 다음 당신의 전화번호의 뒷자리(예를들어 전화번호가 010-1234-5678이라면 5678)를 더해주세요

## 또 더해주세요

## 그런다음 2를 나누면...

### Blockquotes

## List Types

### Ordered Lists

1. Item one
   1. sub item one
   2. sub item two
   3. sub item three
2. Item two

### Unordered Lists

* Item one
* Item two
* Item three

## Tables

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3
{: rules="groups"}

## Code Snippets

{% highlight css %}
#container {
  float: left;
  margin: 0 -240px 0 0;
  width: 100%;
}
{% endhighlight %}

## Buttons

Make any link standout more when applying the `.btn` class.

{% highlight html %}
<a href="#" class="btn btn-success">Success Button</a>
{% endhighlight %}

<div markdown="0"><a href="#" class="btn">Primary Button</a></div>
<div markdown="0"><a href="#" class="btn btn-success">Success Button</a></div>
<div markdown="0"><a href="#" class="btn btn-warning">Warning Button</a></div>
<div markdown="0"><a href="#" class="btn btn-danger">Danger Button</a></div>
<div markdown="0"><a href="#" class="btn btn-info">Info Button</a></div>

## KBD

You can also use `<kbd>` tag for keyboard buttons.

{% highlight html %}
<kbd>W</kbd><kbd>A</kbd><kbd>S</kbd><kbd>D</kbd>
{% endhighlight %}

Press <kbd>W</kbd><kbd>A</kbd><kbd>S</kbd><kbd>D</kbd> to move your car. **Midtown Maddness!!**

## Notices

**Watch out!** You can also add notices by appending `{: .notice}` to a paragraph.
{: .notice}
