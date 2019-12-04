---
title: Derleyici hatası C3283
ms.date: 11/04/2016
f1_keywords:
- C3283
helpviewer_keywords:
- C3283
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
ms.openlocfilehash: a1aa7a0744c2eca2101931ba9ef0ad6ee212d5a7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757572"
---
# <a name="compiler-error-c3283"></a>Derleyici hatası C3283

' Type ': bir arabirimin örnek Oluşturucusu olamaz

CLR [arabiriminin](../../extensions/interface-class-cpp-component-extensions.md) örnek Oluşturucusu olamaz.  Statik oluşturucuya izin verilir.

Aşağıdaki örnek C3283 oluşturur:

```cpp
// C3283.cpp
// compile with: /clr
interface class I {
   I();   // C3283
};
```

Olası çözüm:

```cpp
// C3283b.cpp
// compile with: /clr /c
interface class I {
   static I(){}
};
```
