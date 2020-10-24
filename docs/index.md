# MkDocs Sample

本ページのレンダリングには[MkDocs](https://www.mkdocs.org/)を利用しています。
また、MkDocsのテーマとして[mkdocs-material](https://squidfunk.github.io/mkdocs-material/)を利用しています。

## 手元でビルドして表示確認をする方法

mkdocsを動作させるためにはPython3が必要となります。

まず必要なパッケージをインストールします。

```bash
$ pip3 install -r requirements.txt
```

ビルドします。

```bash
$ mkdocs build
```

ローカルにサーバーを立てます。

```bash
$ mkdocs serve
```

ブラウザで http://localhost:8000/ にアクセスすると表示を確認することができます。
なおmarkdownを編集すると自動でリビルド＆リロードされるので立ち上げ直す必要はありません。

## 拡張

いくつかのMkDocs拡張を導入しています。

### admonition

tipsなどを表記するための拡張です。  

```
!!! Note
    これはノートです。

!!! Tip
    これはコツです。

!!! Warning
    これは警告です。

!!! Bug
    これはバグです。

!!! Success
    これは成功します。

!!! Failure
    これは失敗します。
```

!!! Note
    これはノートです。

!!! Tip
    これはコツです。

!!! Warning
    これは警告です。

!!! Bug
    これはバグです。

!!! Success
    これは成功します。

!!! Failure
    これは失敗します。

### plantuml

`::uml::`と`::end-uml::`で囲むことで、PlantUMLをmarkdownに直接記述することができます。

```
start
if (condition A) then (yes)
  :Text 1;
elseif (condition B) then (yes)
  :Text 2;
  stop
elseif (condition C) then (yes)
  :Text 3;
elseif (condition D) then (yes)
  :Text 4;
else (nothing)
  :Text else;
endif
stop
```

::uml::
start
if (condition A) then (yes)
  :Text 1;
elseif (condition B) then (yes)
  :Text 2;
  stop
elseif (condition C) then (yes)
  :Text 3;
elseif (condition D) then (yes)
  :Text 4;
else (nothing)
  :Text else;
endif
stop
::end-uml::

```
actor actor
agent agent
artifact artifact
boundary boundary
card card
cloud cloud
component component
control control
database database
entity entity
file file
folder folder
frame frame
interface  interface
node node
package package
queue queue
stack stack
rectangle rectangle
storage storage
usecase usecase
```

::uml::
actor actor
agent agent
artifact artifact
boundary boundary
card card
cloud cloud
component component
control control
database database
entity entity
file file
folder folder
frame frame
interface  interface
node node
package package
queue queue
stack stack
rectangle rectangle
storage storage
usecase usecase
::end-uml::

```
package "Some Group" {
  HTTP - [First Component]
  [Another Component]
}
 
node "Other Groups" {
  FTP - [Second Component]
  [First Component] --> FTP
} 

cloud {
  [Example 1]
}


database "MySql" {
  folder "This is my folder" {
    [Folder 3]
  }
  frame "Foo" {
    [Frame 4]
  }
}


[Another Component] --> [Example 1]
[Example 1] --> [Folder 3]
[Folder 3] --> [Frame 4]
```

::uml::
package "Some Group" {
  HTTP - [First Component]
  [Another Component]
}
 
node "Other Groups" {
  FTP - [Second Component]
  [First Component] --> FTP
} 

cloud {
  [Example 1]
}


database "MySql" {
  folder "This is my folder" {
    [Folder 3]
  }
  frame "Foo" {
    [Frame 4]
  }
}


[Another Component] --> [Example 1]
[Example 1] --> [Folder 3]
[Folder 3] --> [Frame 4]
::end-uml::

```
[Prototype design] lasts 10 days
[Code prototype] lasts 10 days
[Write tests] lasts 5 days
[Code prototype] starts at [Prototype design]'s end
[Write tests] starts at [Code prototype]'s start
```

::uml::
[Prototype design] lasts 10 days
[Code prototype] lasts 10 days
[Write tests] lasts 5 days
[Code prototype] starts at [Prototype design]'s end
[Write tests] starts at [Code prototype]'s start
::end-uml::

他のサンプルは[仕様](http://plantuml.com/sitemap-language-specification)をみてください。

### PyMdown

[PyMdown](https://facelessuser.github.io/pymdown-extensions/)によりいろいろな拡張が使えます。

#### emoji
```
:beer: :smile: :sushi:
```

:beer: :smile: :sushi:

#### mark
```
==ここ、テストに出ます！==
```

==ここ、テストに出ます！==

#### superfences

ソースコードの書式のやつです。
タブで切り替えたりとかもできます。

```Bash tab=
#!/bin/bash
STR="Hello World!"
echo $STR
```

```C tab=
#include 

int main(void) {
  printf("hello, world\n");
}
```

```C++ tab=
#include <iostream>

int main() {
  std::cout << "Hello, world!\n";
  return 0;
}
```

```C# tab=
using System;

class Program {
  static void Main(string[] args) {
    Console.WriteLine("Hello, world!");
  }
}
```

#### MagicLink

URLっぽい文字列を書いておくと自動的にリンクに置き換えてくれます。

https://google.com

明示的にURLであることを示したいのであれば`<>`で囲むことができます。

<https://google.com>


#### tilde

```
いわゆるひとつの ~~打ち消し線~~ というやつでしょうか。
```

いわゆるひとつの ~~打ち消し線~~ というやつでしょうか。


#### details

内容を折りたたんで表示することができます。

```
??? note "詳細はこちら"
    詳細です
```

??? note "詳細はこちら"
    詳細です


また、最初から内容を開いた状態にもできます。

```
???+ note "詳細はこちら"
    詳細です
```

???+ note "詳細はこちら"
    詳細です
