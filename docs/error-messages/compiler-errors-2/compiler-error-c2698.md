---
title: Derleyici Hatası C2698
ms.date: 11/04/2016
f1_keywords:
- C2698
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
ms.openlocfilehash: f643b7d8c035b4d1d7d8806feb5b121cf76d7796
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651921"
---
# <a name="compiler-error-c2698"></a>Derleyici Hatası C2698

using bildirimi için ' 1' bildirimi olamaz birlikte var olan kullanma bildirimi ile var ' bildirimi 2'

Sonra bir [using bildirimi](../../cpp/using-declaration.md) kullanarak herhangi bir veri üyesi için aynı kapsamda aynı adın kullanan bildirimi izin verilmez, yalnızca işlev aşırı yüklenebilir olarak.

Aşağıdaki örnek, C2698 oluşturur:

```
// C2698.cpp
struct A {
   int x;
};

struct B {
   int x;
};

struct C : A, B {
   using A::x;
   using B::x;   // C2698
}
```