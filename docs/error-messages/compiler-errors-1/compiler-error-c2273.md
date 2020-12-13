---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2273'
title: Derleyici hatası C2273
ms.date: 11/04/2016
f1_keywords:
- C2273
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
ms.openlocfilehash: 656b5477682ace779cd872b2233d911cfb67c0e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336263"
---
# <a name="compiler-error-c2273"></a>Derleyici hatası C2273

' Type ': '-> ' işlecinin sağ tarafı olarak geçersizdir

Bir tür, işlecin sağ işleneni olarak görünür `->` .

Bu hata, Kullanıcı tanımlı tür dönüştürmeye erişmeye çalışan bir neden olabilir. **`operator`**-> ile anahtar sözcüğünü kullanın `type` .

Aşağıdaki örnek C2273 oluşturur:

```cpp
// C2273.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};
int main() {
   MyClass * ClassPtr = new MyClass;
   int i = ClassPtr->int();   // C2273
   int j = ClassPtr-> operator int();   // OK
}
```
