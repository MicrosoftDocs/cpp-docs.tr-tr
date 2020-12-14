---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3283'
title: Derleyici hatası C3283
ms.date: 11/04/2016
f1_keywords:
- C3283
helpviewer_keywords:
- C3283
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
ms.openlocfilehash: 577f3fa6c3316c58bf6e9dca94b22a168a451b17
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311883"
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
