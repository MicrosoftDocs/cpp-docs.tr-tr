---
title: Derleyici Hatası C2252
ms.date: 11/04/2016
f1_keywords:
- C2252
helpviewer_keywords:
- C2252
ms.assetid: fee74ab9-1997-4615-82fe-e6d1fe3aacd9
ms.openlocfilehash: 9f24e6dfeb6544e5a6173fd844e3fe8b9ae8698e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62379018"
---
# <a name="compiler-error-c2252"></a>Derleyici Hatası C2252

Şablon geçerli kapsamda açıkça örneği oluşturulamıyor

Derleyici, bir şablonun açıkça örneğinin ile ilgili bir sorun algıladı.  Örneğin, bir işlev şablonunun açıkça örneği oluşturulamıyor.

Aşağıdaki örnek, C2252 oluşturur:

```
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