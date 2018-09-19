---
title: Derleyici Hatası C2698 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2698
dev_langs:
- C++
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7ca3e7568640aabd2b7960d97ea94a11a1d5d59
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118927"
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