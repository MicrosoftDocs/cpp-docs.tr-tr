---
title: Derleyici hatası C2698
ms.date: 11/04/2016
f1_keywords:
- C2698
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
ms.openlocfilehash: 6129ff691f804b31fdb8cb487ac4609e4bca6ef2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755193"
---
# <a name="compiler-error-c2698"></a>Derleyici hatası C2698

' declaration 1 ' için using bildirimi, ' declaration 2 ' için var olan using bildirimiyle birlikte bulunamaz

Bir veri üyesi için bir [using bildirimi](../../cpp/using-declaration.md) olduktan sonra, yalnızca işlevler aşırı yüklenmiş olabilir, ancak aynı ada sahip olan aynı kapsamdaki kullanım bildirimine izin verilmez.

Aşağıdaki örnek C2698 oluşturur:

```cpp
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
