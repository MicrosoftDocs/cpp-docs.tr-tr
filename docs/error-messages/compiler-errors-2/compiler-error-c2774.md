---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2774'
title: Derleyici hatası C2774
ms.date: 11/04/2016
f1_keywords:
- C2774
helpviewer_keywords:
- C2774
ms.assetid: 10f428c6-7f49-489a-92ba-6ef978b7caaf
ms.openlocfilehash: d934b2f85fe571c43c8db69018c7c13fd782226a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298207"
---
# <a name="compiler-error-c2774"></a>Derleyici hatası C2774

' tanımlayıcı ': Bu özellikle ilişkili hiçbir ' Put ' yöntemi yok

[Özelliği](../../cpp/property-cpp.md) ile belirtilen bir veri üyesinin işlevi yok `put` , ancak bir ifade değerini ayarlamaya çalışıyor.

Aşağıdaki örnek C2774 oluşturur:

```cpp
// C2774.cpp
struct A {
   __declspec(property(get=GetProp)) int prop;
   int GetProp(void);

   __declspec(property(get=GetProp2, put=PutProp2)) int prop2;
   int GetProp2(void);
   void PutProp2(int);
};

int main() {
   A* pa = new A;
   int val = 0;
   pa->prop = val;   // C2774
   pa->prop++;   // C2774
}
```
