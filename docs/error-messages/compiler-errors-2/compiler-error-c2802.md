---
title: Derleyici Hatası C2802
ms.date: 11/04/2016
f1_keywords:
- C2802
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
ms.openlocfilehash: 9024a13b0e4fdbc4174f94e6c0c8736b03f3c221
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538742"
---
# <a name="compiler-error-c2802"></a>Derleyici Hatası C2802

statik üye 'operator işleci' hiç biçimsel parametresi yok

Bir işleç tarafından bildirilen bir `static` üye işlevi, en az bir parametresi olmalıdır.

Aşağıdaki örnek, C2802 oluşturur:

```
// C2802.cpp
// compile with: /clr /c
ref class A {
   static operator+ ();   // C2802
   static operator+ (A^, A^);   // OK
};
```