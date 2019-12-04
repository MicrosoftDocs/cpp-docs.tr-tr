---
title: Derleyici hatası C2258
ms.date: 11/04/2016
f1_keywords:
- C2258
helpviewer_keywords:
- C2258
ms.assetid: 105eaa87-befb-4ecb-9a3f-e09e14d2f5bf
ms.openlocfilehash: 916ccf444bf82c9d6c0c9ad290afb65353a4f5b2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758807"
---
# <a name="compiler-error-c2258"></a>Derleyici hatası C2258

geçersiz saf sözdizimi; ' = 0 ' olmalıdır

Saf sanal işlev yanlış sözdizimine göre bildiriliyor.

Aşağıdaki örnek C2258 oluşturur:

```cpp
// C2258.cpp
// compile with: /c
class A {
public:
   void virtual func1() = 1; // C2258
   void virtual func2() = 0;   // OK
};
```
