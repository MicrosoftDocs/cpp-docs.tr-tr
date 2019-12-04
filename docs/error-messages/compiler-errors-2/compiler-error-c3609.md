---
title: Derleyici hatası C3609
ms.date: 11/04/2016
f1_keywords:
- C3609
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
ms.openlocfilehash: 1d3078614ff6818dd4185b3bd5ed2f49413db16f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755960"
---
# <a name="compiler-error-c3609"></a>Derleyici hatası C3609

' üye ': korumalı veya son işlevin sanal olması gerekir

[Sealed](../../extensions/sealed-cpp-component-extensions.md) ve [final](../../cpp/final-specifier.md) anahtar sözcüklere yalnızca `virtual`olarak işaretlenmiş bir sınıf, yapı veya üye işlevinde izin verilir.

Aşağıdaki örnek C3609 oluşturur:

```cpp
// C3609.cpp
// compile with: /clr /c
ref class C {
   int f() sealed;   // C3609
   virtual int f2() sealed;   // OK
};
```
