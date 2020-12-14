---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2293'
title: Derleyici hatası C2293
ms.date: 11/04/2016
f1_keywords:
- C2293
helpviewer_keywords:
- C2293
ms.assetid: 17e7b4e2-368b-4dd7-a01b-d82be60f8e56
ms.openlocfilehash: 667ca42295092711f5812d2d7d0b10afb82e9959
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235261"
---
# <a name="compiler-error-c2293"></a>Derleyici hatası C2293

' tanımlayıcı ': bir üye değişkenine __based tanımlayıcısı olarak izin geçersizdir

Değiştirici belirticileri **`__based`** üye olmayan işaretçiler olmalıdır.

Aşağıdaki örnek C2293 oluşturur:

```cpp
// C2293.cpp
// compile with: /c
class A {
   static int *i;
   void __based(i) *bp;   // C2293
   void *bp2;   // OK
};
```
