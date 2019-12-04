---
title: Derleyici hatası C3262
ms.date: 11/04/2016
f1_keywords:
- C3262
helpviewer_keywords:
- C3262
ms.assetid: 3e74b9aa-de3c-4492-9331-ee73012b958b
ms.openlocfilehash: 8f810cb300ab6db61cc6188aa5e9427ed2141338
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754205"
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
