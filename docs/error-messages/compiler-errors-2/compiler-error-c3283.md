---
title: Derleyici Hatası C3283
ms.date: 11/04/2016
f1_keywords:
- C3283
helpviewer_keywords:
- C3283
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
ms.openlocfilehash: 593b04b8593e261aa1980ada7693300b52a869c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381585"
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