---
title: Derleyici Hatası C2561
ms.date: 11/04/2016
f1_keywords:
- C2561
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
ms.openlocfilehash: 8350c5baf129b88c178be280d2da7fe856c6cf57
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368428"
---
# <a name="compiler-error-c2561"></a>Derleyici Hatası C2561

'identifier': işlev bir değer döndürmelidir

İşlev değer döndürüyor olarak bildirildi, ancak işlev tanımı içermediğinden bir `return` deyimi.

Bu hata, bir hatalı işlev prototipi tarafından kaynaklanabilir:

1. İşlev bir değer döndürmezse işlevi dönüş türüyle bildirin [void](../../cpp/void-cpp.md).

1. İşlevin tüm olası dalları prototip türünde bildirilen bir değer döndüren denetleyin.

1. Dönüş değeri saklamak satır içi bütünleştirilmiş kod yordamlarını içeren C++ işlevlerini `AX` kaydı, bir return deyimi gerekebilir. Değeri kopyalamak `AX` geçici bir değişkene ve bu değişkeni işlevden döndürür.

Aşağıdaki örnek, C2561 oluşturur:

```
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