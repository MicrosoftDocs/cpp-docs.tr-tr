---
title: Derleyici Hatası C3902
ms.date: 11/04/2016
f1_keywords:
- C3902
helpviewer_keywords:
- C3902
ms.assetid: feb3bb29-f836-4d77-ba71-3876f7f4f216
ms.openlocfilehash: d90bf299c566ce72e3d1cbfeb545def0a43d6cbf
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776303"
---
# <a name="compiler-error-c3902"></a>Derleyici Hatası C3902

'erişimcisi': son parametrenin türü 'type' olmalıdır

En az bir kümesi yönteminin son parametrenin türü özellik türü eşleşmelidir. Daha fazla bilgi için [özelliği](../../extensions/property-cpp-component-extensions.md).

Aşağıdaki örnek, C3902 oluşturur:

```
// C3902.cpp
// compile with: /clr /c
using namespace System;
ref class X {
   property String ^Name {
      void set(int);   // C3902
      // try the following line instead
      // void set(String^){}
   }

   property double values[int,int] {
      void set(int, int, float);   // C3902
      // try the following line instead
      // void set(int, int, double){}
   }
};
```