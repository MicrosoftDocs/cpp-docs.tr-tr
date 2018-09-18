---
title: Derleyici Hatası C3240 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3240
dev_langs:
- C++
helpviewer_keywords:
- C3240
ms.assetid: 1a8dc213-b80c-47ae-ada0-e9554b635d1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9898d67bbe92e3ba93ec08bdbb68f11d81483c69
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023910"
---
# <a name="compiler-error-c3240"></a>Derleyici Hatası C3240

'function': 'type' aşırı yüklenmemiş bir soyut üye işlevi olmalıdır

Bir taban türü tanımlanmış bir işlev içeriyordu. İşlev sanal olmalıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3240 oluşturur.

```
// C3240.cpp
// compile with: /c
__interface I {
   void f();
};

struct A1 : I {
   void f() {}
};

struct A2 : I {
   void f() = 0;
};

template <class T>
struct A3 : T {
   void T::f() {}
};

template <class T>
struct A4 : T {
   void T::f() {}
};

A3<A1> x;   // C3240
A3<I> x2;
A4<A2> x3;
```