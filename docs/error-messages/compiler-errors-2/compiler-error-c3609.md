---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3609'
title: Derleyici hatası C3609
ms.date: 11/04/2016
f1_keywords:
- C3609
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
ms.openlocfilehash: 187bc6d9849c385f6adb3ae2c25e2e90e7393e6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223132"
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
