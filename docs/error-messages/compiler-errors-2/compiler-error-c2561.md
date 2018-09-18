---
title: Derleyici Hatası C2561 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2561
dev_langs:
- C++
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8611af23ab884a853fc751ae82c636753993495b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070710"
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