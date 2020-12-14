---
description: 'Daha fazla bilgi edinin: C bildirimleri ve tanımları'
title: C Tanımları ve Bildirimleri
ms.date: 11/04/2016
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
ms.openlocfilehash: dac53ac203c8e58e3af87e4869983c0443ffb092
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254319"
---
# <a name="c-declarations-and-definitions"></a>C Tanımları ve Bildirimleri

Bir "bildirim" belirli bir değişken, işlev veya tür ve öznitelikleri arasında bir ilişki kurar. [Bildirimlere genel bakış](../c-language/overview-of-declarations.md) , Terminal DıŞı için ANSI söz dizimini verir `declaration` . Bir bildirim, bir tanımlayıcıya nereden ve ne zaman erişilebileceğini de belirtir (bir tanımlayıcının "bağlantısı"). Bağlantı hakkında bilgi için bkz. [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md) .

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

[Kaynak dosyalar ve kaynak programlar](../c-language/source-files-and-source-programs.md)
