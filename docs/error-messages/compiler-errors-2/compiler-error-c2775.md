---
title: Derleyici Hatası C2775
ms.date: 11/04/2016
f1_keywords:
- C2775
helpviewer_keywords:
- C2775
ms.assetid: 9c488508-ade0-48f1-b94f-d538d15f807a
ms.openlocfilehash: b0f04a64354f549115c8636cf6130d6e96470016
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257198"
---
# <a name="compiler-error-c2775"></a>Derleyici Hatası C2775

'identifier': Bu özellikle ilişkili hiçbir 'get' yöntemi

Bir veri üyesi ile bildirilen [özelliği](../../cpp/property-cpp.md) genişletilmiş öznitelik yok bir `get` işlevi belirtildi, ancak bir ifadenin, değerini almayı dener.

Aşağıdaki örnek, C2775 oluşturur:

```
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