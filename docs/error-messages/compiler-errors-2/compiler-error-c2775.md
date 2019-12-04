---
title: Derleyici hatası C2775
ms.date: 11/04/2016
f1_keywords:
- C2775
helpviewer_keywords:
- C2775
ms.assetid: 9c488508-ade0-48f1-b94f-d538d15f807a
ms.openlocfilehash: be858c7508aa520f78ec144b02738af02099b49b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740058"
---
# <a name="compiler-error-c2775"></a>Derleyici hatası C2775

' tanımlayıcı ': Bu özellikle ilişkili hiçbir ' Get ' yöntemi yok

Genişletilmiş öznitelik [özelliği](../../cpp/property-cpp.md) ile belirtilen bir veri üyesinin bir `get` işlevi yok, ancak bir ifade değeri almaya çalışıyor.

Aşağıdaki örnek C2775 oluşturur:

```cpp
// C2775.cpp
struct A {
   __declspec(property(put=PutProp2, get=GetProp2)) int prop2;
   int GetProp2(){return 0;}
   void PutProp2(int){}

   __declspec(property(put=PutProp)) int prop;
   int PutProp(void){}

};

int main() {
   A* pa = new A;
   int x;
   x = pa->prop;   // C2775
   x = pa->prop2;
}
```
