---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3262'
title: Derleyici hatası C3262
ms.date: 11/04/2016
f1_keywords:
- C3262
helpviewer_keywords:
- C3262
ms.assetid: 3e74b9aa-de3c-4492-9331-ee73012b958b
ms.openlocfilehash: 9d1b4954f4f015c5dad584a5e6a124bc7d4bd155
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223457"
---
# <a name="compiler-error-c3262"></a>Derleyici hatası C3262

geçersiz dizi dizini oluşturma: ' # '-boyutlu ' dizi türü ' için ' # ' boyut belirtildi

Dizi yanlış bir şekilde kaldırıldı. Dizin sayısı dizideki boyut sayısıyla eşleşmeyebilir.

Aşağıdaki örnek C3262 oluşturur:

```cpp
// C3262.cpp
// compile with: /clr
#using <mscorlib.dll>
using namespace System;

#define ARRAY_SIZE 2

ref class MyClass {
public:
   int m_i;
};

// returns a multidimensional managed array of a reference type
array<MyClass^, 2>^ Test0() {
   int i, j;
   array< MyClass^, 2 >^ local = new array< MyClass^, 2 >
      (ARRAY_SIZE, ARRAY_SIZE);

   for (i = 0 ; i < ARRAY_SIZE ; i++)
      for (j = 0 ; j < ARRAY_SIZE ; j++) {
         local[i][j] = new MyClass;   // C3262
         // try the following line instead
         // local[i,j] = new MyClass;
         local[i,j] -> m_i = i;
      }

      return local;
}

int main() {
   int i, j;

   array< MyClass^, 2 >^ MyClass0;
   MyClass0 = Test0();
}
```
