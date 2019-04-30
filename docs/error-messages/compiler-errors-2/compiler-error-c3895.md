---
title: Derleyici Hatası C3895
ms.date: 11/04/2016
f1_keywords:
- C3895
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
ms.openlocfilehash: c4b1cad9ef48f1f16b411aab46e1bb9285d69ff3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385543"
---
# <a name="compiler-error-c3895"></a>Derleyici Hatası C3895

'var': tür veri üyeleri 'volatile' olamaz

Belirli türde bir örnek için veri üye [değişmez değer](../../extensions/literal-cpp-component-extensions.md) veya [initonly](../../dotnet/initonly-cpp-cli.md), olamaz [geçici](../../cpp/volatile-cpp.md).

Aşağıdaki örnek, C3895 oluşturur:

```
// C3895.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   volatile int data_var2;   // C3895
};
```