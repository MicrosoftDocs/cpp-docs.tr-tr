---
title: Derleyici Hatası C3866
ms.date: 11/04/2016
f1_keywords:
- C3866
helpviewer_keywords:
- C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
ms.openlocfilehash: 98014fec77ce47fa4c484645f401e615f1470e2f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446299"
---
# <a name="compiler-error-c3866"></a>Derleyici Hatası C3866

bağımsız değişken listesi eksik işlev çağrısı

Bir statik olmayan üye işlev içinde bir yıkıcı veya Sonlandırıcı çağrısı bir bağımsız değişken listesi yok.

Aşağıdaki örnek, C3866 oluşturur:

```
// C3866.cpp
// compile with: /c
class C {
   ~C();
   void f() {
      this->~C;   // C3866
      this->~C();   // OK
   }
};
```