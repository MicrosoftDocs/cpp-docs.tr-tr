---
title: Derleyici Hatası C2502
ms.date: 11/04/2016
f1_keywords:
- C2502
helpviewer_keywords:
- C2502
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
ms.openlocfilehash: e23ccae55c40c9652f5a3e1f55c834a968bca784
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601623"
---
# <a name="compiler-error-c2502"></a>Derleyici Hatası C2502

'identifier': taban sınıfta çok fazla erişim değiştiricileri

Temel sınıfın birden fazla erişim değiştiricisi vardır. Yalnızca bir erişim belirleyici (`public`, `private`, veya `protected`) izin verilir.

Aşağıdaki örnek, C2502 oluşturur:

```
// C2502.cpp
// compile with: /c
class A { };
class B { };
class C : private public A { };   // C2502

// OK
class D : private A {};
class E : public A, private B {};
```