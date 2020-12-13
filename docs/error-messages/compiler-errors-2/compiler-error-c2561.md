---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2561'
title: Derleyici hatası C2561
ms.date: 11/04/2016
f1_keywords:
- C2561
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
ms.openlocfilehash: 11ec708d25af9fc9603977c33741a1f74a406e92
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144878"
---
# <a name="compiler-error-c2561"></a>Derleyici hatası C2561

' tanımlayıcı ': işlev bir değer döndürmelidir

İşlev bir değer döndürüyor olarak bildirildi, ancak işlev tanımı bir **`return`** ifade içermiyor.

Bu hata yanlış bir işlev prototipten kaynaklanıyor olabilir:

1. İşlev bir değer döndürmezse, işlevi [void](../../cpp/void-cpp.md)dönüş türü ile bildirin.

1. İşlevin tüm olası dallarında, prototipte belirtilen türün bir değerini döndürmediğine bakın.

1. Kayıt içinde dönüş değerini depolayan satır içi derleme yordamlarını içeren C++ işlevleri `AX` , return ifadesine gerek duyar. İçindeki değeri `AX` geçici bir değişkene kopyalayın ve bu değişkeni işlevden döndürün.

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
