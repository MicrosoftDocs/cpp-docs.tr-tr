---
title: Derleyici hatası C3609
ms.date: 11/04/2016
f1_keywords:
- C3609
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
ms.openlocfilehash: 2eff238aed756c9f056da9a1b9a70fca9de24fa3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230811"
---
# <a name="compiler-error-c3609"></a>Derleyici hatası C3609

' üye ': korumalı veya son işlevin sanal olması gerekir

[Sealed](../../extensions/sealed-cpp-component-extensions.md) ve [final](../../cpp/final-specifier.md) anahtar kelimelerinde yalnızca bir sınıf, yapı veya işaretlenmiş üye işlevinde izin verilir **`virtual`** .

Aşağıdaki örnek C3609 oluşturur:

```cpp
// C3609.cpp
// compile with: /clr /c
ref class C {
   int f() sealed;   // C3609
   virtual int f2() sealed;   // OK
};
```
