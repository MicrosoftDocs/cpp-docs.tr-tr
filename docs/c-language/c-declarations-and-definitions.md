---
title: C tanımları ve bildirimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fcb83395313609fc5c9bad673416131b2332552
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019568"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Dosyalar ve Kaynak Programlar](../c-language/source-files-and-source-programs.md)