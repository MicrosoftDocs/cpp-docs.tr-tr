---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2698'
title: Derleyici hatası C2698
ms.date: 11/04/2016
f1_keywords:
- C2698
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
ms.openlocfilehash: a787c43e7a885734f4c6a2d76aa16d51e19615c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326636"
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
