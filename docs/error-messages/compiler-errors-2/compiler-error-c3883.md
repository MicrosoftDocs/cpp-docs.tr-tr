---
title: Derleyici hatası C3883
ms.date: 11/04/2016
f1_keywords:
- C3883
helpviewer_keywords:
- C3883
ms.assetid: cdd1c1f4-f268-4469-9c62-d52303114b0c
ms.openlocfilehash: 9dbb0328aa1810d55f2d974aed822992b53101b5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736665"
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
