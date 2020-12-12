---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4937'
title: Derleyici Uyarısı (düzey 4) C4937
ms.date: 11/04/2016
f1_keywords:
- C4937
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
ms.openlocfilehash: fa614e9f93cf83afbe3ff46e624f13b5199a28d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251251"
---
# <a name="compiler-warning-level-4-c4937"></a>Derleyici Uyarısı (düzey 4) C4937

' Metin1 ' ve ' Metin2 ', ' Directive ' için bağımsız değişkenler olarak ayırt edilemez

Derleyicinin yönergeleri için bağımsız değişkenleri işlediği şekilde, birden çok metin gösterimiyle (tek veya çift alt çizgi formlar) anahtar sözcükler gibi, derleyiciye anlamı olan adlar ayırt edilemez.

Bu tür dizelerin örnekleri __cdecl ve \_ _forceinline.  Bkz./za altında yalnızca çift alt çizgi formları etkindir.

Aşağıdaki örnek C4937 oluşturur:

```cpp
// C4937.cpp
// compile with: /openmp /W4
#include "omp.h"
int main() {
   #pragma omp critical ( __leave )   // C4937
   ;

   // OK
   #pragma omp critical ( leave )
   ;
}
```
