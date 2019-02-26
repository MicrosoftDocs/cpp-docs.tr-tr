---
title: C Tanımları ve Bildirimleri
ms.date: 11/04/2016
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
ms.openlocfilehash: 3be9cd72e9f4dbad4d279cc1bb65dfb92a61cd42
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56150526"
---
# <a name="c-declarations-and-definitions"></a>C Tanımları ve Bildirimleri

Bir "bildirim" belirli bir değişken, işlev veya tür ve öznitelikleri arasında bir ilişki kurar. [Bildirimlere genel bakış](../c-language/overview-of-declarations.md) yönelik ANSI sözdizimini sağlar `declaration` bildirimlere. Bir bildirim, bir tanımlayıcıya nereden ve ne zaman erişilebileceğini de belirtir (bir tanımlayıcının "bağlantısı"). Bkz: [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md) bağlantı hakkında bilgi için.

Bir değişkenin "tanımı" bildirimle aynı ilişkileri kurar, ancak depolamanın değişken için ayrılmasına da neden olur.

Örneğin, `main`, `find` ve `count` işlevleri ve `var` ve `val` değişkenleri aşağıdaki sırayla bir kaynak dosyasında tanımlanır:

```
int main() {}

int var = 0;
double val[MAXVAL];
char find( fileptr ) {}
int count( double f ) {}
```

`var` ve `val` değişkenleri `find` ve `count` işlevlerinde kullanılır; başka bildirime gerek yoktur. Ancak bu adlar `main`'de görünmez (erişilemez).

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalar ve Kaynak Programlar](../c-language/source-files-and-source-programs.md)
