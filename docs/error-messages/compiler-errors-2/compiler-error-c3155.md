---
title: Derleyici Hatası C3155
ms.date: 11/04/2016
f1_keywords:
- C3155
helpviewer_keywords:
- C3155
ms.assetid: b04a42e1-64e7-40f8-81fe-c7945348b2cf
ms.openlocfilehash: 85ee53dff7ae50717eabfd1ac6504ebb74deaa2d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374852"
---
# <a name="compiler-error-c3155"></a>Derleyici Hatası C3155

özellik dizini oluşturucuda özniteliklere izin verilmez

Dizini oluşturulmuş özelliğe yanlış bildirildi. Daha fazla bilgi için [nasıl yapılır: İçindeki özellikleri kullanın C++/CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3155 oluşturur.

```
// C3155.cpp
// compile with: /clr /c
using namespace System;
ref struct R {
   property int F[[ParamArray] int] {   // C3155
   // try the following line instead
   // property int F[ int] {   // OK
      int get(int i) {
         return 0;
      }
   }
};
```