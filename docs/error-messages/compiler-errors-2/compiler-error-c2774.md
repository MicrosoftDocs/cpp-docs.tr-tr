---
title: Derleyici Hatası C2774
ms.date: 11/04/2016
f1_keywords:
- C2774
helpviewer_keywords:
- C2774
ms.assetid: 10f428c6-7f49-489a-92ba-6ef978b7caaf
ms.openlocfilehash: 6197e3da81a9f059c90d15608a939ad4887e526d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257146"
---
# <a name="compiler-error-c2774"></a>Derleyici Hatası C2774

'identifier': Bu özellikle ilişkili hiçbir 'put' yöntemi

Bir veri üyesi ile bildirilen [özelliği](../../cpp/property-cpp.md) hiçbir `put` işlevi, ancak bir ifadenin değerini ayarlama dener.

Aşağıdaki örnek, C2774 oluşturur:

```
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