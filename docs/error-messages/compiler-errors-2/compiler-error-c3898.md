---
title: Derleyici Hatası C3898
ms.date: 11/04/2016
f1_keywords:
- C3898
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
ms.openlocfilehash: 503f295d62c598e3138b1a001d6b350c0d90ea84
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385452"
---
# <a name="compiler-error-c3898"></a>Derleyici Hatası C3898

'var': tür veri üyeleri yalnızca yönetilen türlerin üyeleri olabilir

Bir [initonly](../../dotnet/initonly-cpp-cli.md) veri üyesi, bir yerel sınıf içinde bildirildi.  Bir `initonly` veri üyesi yalnızca bir CLR sınıfında bildirilebilir.

Aşağıdaki örnek, C3898 oluşturur:

```
// C3898.cpp
// compile with: /clr
struct Y1 {
   initonly
   static int data_var = 9;   // C3898
};
```

Olası çözüm:

```
// C3898b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int data_var = 9;
};
```