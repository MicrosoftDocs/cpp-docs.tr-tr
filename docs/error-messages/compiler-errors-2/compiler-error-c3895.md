---
title: Derleyici Hatası C3895
ms.date: 11/04/2016
f1_keywords:
- C3895
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
ms.openlocfilehash: 61dd280caa3c8c9b28dd77ecab2ed50ab9532d4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501290"
---
# <a name="compiler-error-c3895"></a>Derleyici Hatası C3895

'var': tür veri üyeleri 'volatile' olamaz

Belirli türde bir örnek için veri üye [değişmez değer](../../windows/literal-cpp-component-extensions.md) veya [initonly](../../dotnet/initonly-cpp-cli.md), olamaz [geçici](../../cpp/volatile-cpp.md).

Aşağıdaki örnek, C3895 oluşturur:

```
// C3895.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   volatile int data_var2;   // C3895
};
```