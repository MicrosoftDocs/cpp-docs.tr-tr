---
title: Derleyici hatası C2380
ms.date: 11/04/2016
f1_keywords:
- C2380
helpviewer_keywords:
- C2380
ms.assetid: 717b1e6e-ddfe-4bac-a5f3-7f9a4dcb1572
ms.openlocfilehash: ca249bc592bd66c2e461a37fdc18204077f51db2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745440"
---
# <a name="compiler-error-c2380"></a>Derleyici hatası C2380

' Identifier ' öncesinde tür (dönüş türü olan Oluşturucu veya geçerli sınıf adı için geçersiz yeniden tanımlama mi var?)

Bir Oluşturucu bir değer döndürür veya sınıf adını tekrar tanımlar.

Aşağıdaki örnek C2326 oluşturur:

```cpp
// C2380.cpp
// compile with: /c
class C {
public:
   int C();   // C2380, specifies an int return
   int C;   // C2380, redefinition of i
   C();   // OK
};
```
