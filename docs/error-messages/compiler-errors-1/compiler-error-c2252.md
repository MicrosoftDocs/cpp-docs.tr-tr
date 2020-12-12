---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2252'
title: Derleyici hatası C2252
ms.date: 11/04/2016
f1_keywords:
- C2252
helpviewer_keywords:
- C2252
ms.assetid: fee74ab9-1997-4615-82fe-e6d1fe3aacd9
ms.openlocfilehash: 491ec4c600ab480322917d50822ede01a08dcfb5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134829"
---
# <a name="compiler-error-c2252"></a>Derleyici hatası C2252

geçerli kapsamda şablon açıkça başlatılamaz

Derleyici, bir şablonun açık örneklemesi ile ilgili bir sorun algıladı.  Örneğin, bir işlevde açıkça bir şablonu örnekleyemezsiniz.

Aşağıdaki örnek C2252 oluşturur:

```cpp
// C2252.cpp
class A {
public:
   template <class T>
   int getit(int i , T * it ) {
      return i;
   }
   template int A::getit<double>(int i, double * it);   // C2252
   // try the following line instead
   // template <> int A::getit<double>(int i, double * it);

};

int main() {
   // cannot explicitly instantiate in function
   template int A::getit<long>(int i, long * it);   // C2252
}
```
