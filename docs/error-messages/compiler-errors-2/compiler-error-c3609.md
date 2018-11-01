---
title: Derleyici Hatası C3609
ms.date: 11/04/2016
f1_keywords:
- C3609
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
ms.openlocfilehash: 5572f39082e2dcd8746bb464595c5c00e2f77356
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556451"
---
# <a name="compiler-error-c3609"></a>Derleyici Hatası C3609

'member': sealed veya son bir işlev sanal olmalıdır

[Korumalı](../../windows/sealed-cpp-component-extensions.md) ve [son](../../cpp/final-specifier.md) anahtar sözcükler yalnızca bir sınıf, yapı veya üye işlev işaretlenmiş izin `virtual`.

Aşağıdaki örnek, C3609 oluşturur:

```
// C3609.cpp
// compile with: /clr /c
ref class C {
   int f() sealed;   // C3609
   virtual int f2() sealed;   // OK
};
```
