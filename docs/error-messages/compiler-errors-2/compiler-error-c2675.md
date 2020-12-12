---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2675'
title: Derleyici hatası C2675
ms.date: 11/04/2016
f1_keywords:
- C2675
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
ms.openlocfilehash: 71d52a8da09861078811757ad7af7c757e418e5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282035"
---
# <a name="compiler-error-c2675"></a>Derleyici hatası C2675

Birli ' operator ': ' Type ' Bu işleci veya önceden tanımlanmış işleç için kabul edilebilir bir türe dönüştürmeyi tanımlamıyor

C2675, birli bir operatör kullanılırken da gerçekleşebilir ve tür işleci veya önceden tanımlanmış işleç için kabul edilebilir bir türe dönüştürmeyi tanımlamaz. İşlecini kullanmak için, belirtilen tür için onu tekrar yüklemelisiniz veya işlecin tanımlandığı bir türe dönüştürme tanımlamanız gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2675 oluşturur.

```cpp
// C2675.cpp
struct C {
   C(){}
} c;

struct D {
   D(){}
   void operator-(){}
} d;

int main() {
   -c;   // C2675
   -d;   // OK
}
```
