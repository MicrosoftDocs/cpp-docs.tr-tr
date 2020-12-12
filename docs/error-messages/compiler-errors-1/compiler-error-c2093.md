---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2093'
title: Derleyici hatası C2093
ms.date: 11/04/2016
f1_keywords:
- C2093
helpviewer_keywords:
- C2093
ms.assetid: 17529a70-9169-46b5-9fc6-57a5ce224e6a
ms.openlocfilehash: d08c2e29415363fc64309a89691ec0852ca5fa88
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251862"
---
# <a name="compiler-error-c2093"></a>Derleyici hatası C2093

' variable1 ': ' değişkeni2 ' otomatik değişkeninin adresi kullanılarak başlatılamaz

[/Za](../../build/reference/za-ze-disable-language-extensions.md)ile derlerken, program bir otomatik değişkenin adresini başlatıcı olarak kullanmayı denedi.

Aşağıdaki örnek C2093 oluşturur:

```c
// C2093.c
// compile with: /Za /c
void func() {
   int li;   // an implicit auto variable
   int * s[]= { &li };   // C2093 address is not a constant

   // OK
   static int li2;
   int * s2[]= { &li2 };
}
```
