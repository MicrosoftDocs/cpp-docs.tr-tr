---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3883'
title: Derleyici hatası C3883
ms.date: 11/04/2016
f1_keywords:
- C3883
helpviewer_keywords:
- C3883
ms.assetid: cdd1c1f4-f268-4469-9c62-d52303114b0c
ms.openlocfilehash: 216cfdc6385f12ff565eca581068ac5625a09044
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274430"
---
# <a name="compiler-error-c3883"></a>Derleyici hatası C3883

' var ': initonly bir statik veri üyesinin başlatılması gerekir

[İnitonly](../../dotnet/initonly-cpp-cli.md) ile işaretlenen bir değişken doğru başlatılmamış.

Aşağıdaki örnek C3883 oluşturur:

```cpp
// C3883.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   static int staticConst1;   // C3883
};
```

Aşağıdaki örnekte olası bir çözüm gösterilmektedir:

```cpp
// C3883b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int staticConst2 = 0;
};
```

Aşağıdaki örnek, bir statik oluşturucuda nasıl başlatılacağını göstermektedir:

```cpp
// C3883c.cpp
// compile with: /clr /LD
ref struct Y1 {
   initonly
   static int staticConst1;

   static Y1() {
      staticConst1 = 0;
   }
};
```
