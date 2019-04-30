---
title: Derleyici Hatası C2802
ms.date: 11/04/2016
f1_keywords:
- C2802
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
ms.openlocfilehash: 9024a13b0e4fdbc4174f94e6c0c8736b03f3c221
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408452"
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