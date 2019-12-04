---
title: Derleyici hatası C3803
ms.date: 11/04/2016
f1_keywords:
- C3803
helpviewer_keywords:
- C3803
ms.assetid: bad5fb9a-ed9a-4c15-96e7-cf06e200a50d
ms.openlocfilehash: 771530c2d05d378b86732938aa7a2b7881608446
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755310"
---
# <a name="compiler-error-c3803"></a>Derleyici hatası C3803

' Property ': Özellik erişimcilerinin ' erişimci ' ile uyumsuz bir türe sahip

[Özelliği](../../cpp/property-cpp.md) ile tanımlanmış bir özelliğin türü, erişimci işlevlerinin biri için dönüş türüyle eşleşmiyor.

Aşağıdaki örnek C3803 oluşturur:

```cpp
// C3803.cpp
struct A
{
   __declspec(property(get=GetIt)) int i;
   char GetIt()
   {
      return 0;
   }

   /*
   // try the following definition instead
   int GetIt()
   {
      return 0;
   }
   */
}; // C3803

int main()
{
}
```
