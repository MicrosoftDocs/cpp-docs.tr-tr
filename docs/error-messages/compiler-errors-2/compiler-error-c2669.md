---
title: Derleyici Hatası C2669
ms.date: 11/04/2016
f1_keywords:
- C2669
helpviewer_keywords:
- C2669
ms.assetid: f9cb8111-bcdc-484b-a863-2c42e15a0496
ms.openlocfilehash: 7944ced947ba1d7c8b10172560ce6237a554e236
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649676"
---
# <a name="compiler-error-c2669"></a>Derleyici Hatası C2669

üye işlevi anonim birleşimde izin verilmiyor

[Anonim birleşimler](../../cpp/unions.md#anonymous_unions) üye işlevleri sahip olamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2669 oluşturur:

```cpp
// C2669.cpp
struct X {
   union {
      int i;
      void f() {   // C2669, remove function
         i = 0;
      }
   };
};
```
