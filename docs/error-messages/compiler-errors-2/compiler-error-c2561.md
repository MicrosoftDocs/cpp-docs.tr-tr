---
title: Derleyici hatası C2561
ms.date: 11/04/2016
f1_keywords:
- C2561
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
ms.openlocfilehash: b4a14be9cd32c752e2ab889417494e80b935e31b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755570"
---
# <a name="compiler-error-c2561"></a>Derleyici hatası C2561

' tanımlayıcı ': işlev bir değer döndürmelidir

İşlev bir değer döndürüyor olarak bildirildi, ancak işlev tanımı `return` bir ifade içermiyor.

Bu hata yanlış bir işlev prototipten kaynaklanıyor olabilir:

1. İşlev bir değer döndürmezse, işlevi [void](../../cpp/void-cpp.md)dönüş türü ile bildirin.

1. İşlevin tüm olası dallarında, prototipte belirtilen türün bir değerini döndürmediğine bakın.

1. C++`AX` kaydındaki dönüş değerini depolayan satır içi derleme yordamlarını içeren işlevler, return ifadesine gerek duyar. `AX` değerini geçici bir değişkene kopyalayın ve bu değişkeni işlevden döndürün.

Aşağıdaki örnek C2561 oluşturur:

```cpp
// C2561.cpp
int Test(int x) {
   if (x) {
      return;   // C2561
      // try the following line instead
      // return 1;
   }
   return 0;
}

int main() {
   Test(1);
}
```
