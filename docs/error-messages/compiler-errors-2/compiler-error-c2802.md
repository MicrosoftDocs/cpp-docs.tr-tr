---
title: Derleyici hatası C2802
ms.date: 11/04/2016
f1_keywords:
- C2802
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
ms.openlocfilehash: 12ce65def043a05f5f154130b64326797a974137
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758300"
---
# <a name="compiler-error-c2802"></a>Derleyici hatası C2802

' işleç işleci ' statik üyesinin hiç biçimsel parametresi yok

Bir `static` üye işlevi tarafından tanımlanan bir operatör en az bir parametreye sahip olmalıdır.

Aşağıdaki örnek C2802 oluşturur:

```cpp
// C2802.cpp
// compile with: /clr /c
ref class A {
   static operator+ ();   // C2802
   static operator+ (A^, A^);   // OK
};
```
