---
title: Derleyici Hatası C2534
ms.date: 11/04/2016
f1_keywords:
- C2534
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
ms.openlocfilehash: e684804ea31b16f31c82e244cb4f9a6aaf2d08c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638262"
---
# <a name="compiler-error-c2534"></a>Derleyici Hatası C2534

'identifier': Oluşturucu değer döndüremez

Oluşturucu bir değer döndürür veya bir dönüş türüne sahip (değil bile bir `void` dönüş türü).

Bu hata, kaldırarak düzeltilebilir `return` Oluşturucu tanımı from deyimi.

Aşağıdaki örnek, C2534 oluşturur:

```
// C2534.cpp
class A {
public:
   int i;
   A() { return i; }   // C2534
};
```