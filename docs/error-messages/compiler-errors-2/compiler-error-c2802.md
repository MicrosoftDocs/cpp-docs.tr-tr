---
title: Derleyici hatası C2802
ms.date: 11/04/2016
f1_keywords:
- C2802
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
ms.openlocfilehash: f872a4753907cd78c9118c22498777d5acc5b2fd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214587"
---
# <a name="compiler-error-c2802"></a>Derleyici hatası C2802

' işleç işleci ' statik üyesinin hiç biçimsel parametresi yok

Üye işlevi tarafından tanımlanan bir işlecin **`static`** en az bir parametresi olmalıdır.

Aşağıdaki örnek C2802 oluşturur:

```cpp
// C2802.cpp
// compile with: /clr /c
ref class A {
   static operator+ ();   // C2802
   static operator+ (A^, A^);   // OK
};
```
