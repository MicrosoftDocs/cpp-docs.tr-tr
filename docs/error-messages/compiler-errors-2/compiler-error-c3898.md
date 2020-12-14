---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3898'
title: Derleyici hatası C3898
ms.date: 11/04/2016
f1_keywords:
- C3898
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
ms.openlocfilehash: 4b51683b13fa9328475ba09473ef1cae5663b009
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238966"
---
# <a name="compiler-error-c3898"></a>Derleyici hatası C3898

' var ': tür veri üyeleri yalnızca yönetilen türlerin üyeleri olabilir

Bir [initonly](../../dotnet/initonly-cpp-cli.md) veri üyesi yerel sınıfta bildirildi.  Bir **`initonly`** veri üyesi yalnızca BIR clr sınıfında bildirilebilecek.

Aşağıdaki örnek C3898 oluşturur:

```cpp
// C3898.cpp
// compile with: /clr
struct Y1 {
   initonly
   static int data_var = 9;   // C3898
};
```

Olası çözüm:

```cpp
// C3898b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int data_var = 9;
};
```
