---
title: Derleyici Hatası C3283
ms.date: 11/04/2016
f1_keywords:
- C3283
helpviewer_keywords:
- C3283
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
ms.openlocfilehash: 593b04b8593e261aa1980ada7693300b52a869c5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58779995"
---
# <a name="compiler-error-c3283"></a>Derleyici Hatası C3283

'type': arabirimin örnek oluşturucusu olamaz

Bir CLR [arabirimi](../../extensions/interface-class-cpp-component-extensions.md) örnek oluşturucusu olamaz.  Statik Oluşturucu izin verilir.

Aşağıdaki örnek, C3283 oluşturur:

```
// C3283.cpp
// compile with: /clr
interface class I {
   I();   // C3283
};
```

Olası çözüm:

```
// C3283b.cpp
// compile with: /clr /c
interface class I {
   static I(){}
};
```