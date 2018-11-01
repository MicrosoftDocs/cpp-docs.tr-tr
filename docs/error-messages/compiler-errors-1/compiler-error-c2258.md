---
title: Derleyici Hatası C2258
ms.date: 11/04/2016
f1_keywords:
- C2258
helpviewer_keywords:
- C2258
ms.assetid: 105eaa87-befb-4ecb-9a3f-e09e14d2f5bf
ms.openlocfilehash: 99936026929bbaad321abfaa106df41b99c5d19d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587804"
---
# <a name="compiler-error-c2258"></a>Derleyici Hatası C2258

Geçersiz saf sözdizimi olmalıdır '= 0'

Saf sanal işlevi hatalı sözdizimi ile bildirilir.

Aşağıdaki örnek, C2258 oluşturur:

```
// C2258.cpp
// compile with: /c
class A {
public:
   void virtual func1() = 1; // C2258
   void virtual func2() = 0;   // OK
};
```