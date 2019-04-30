---
title: Derleyici Hatası C2258
ms.date: 11/04/2016
f1_keywords:
- C2258
helpviewer_keywords:
- C2258
ms.assetid: 105eaa87-befb-4ecb-9a3f-e09e14d2f5bf
ms.openlocfilehash: 99936026929bbaad321abfaa106df41b99c5d19d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387058"
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