---
title: Derleyici Hatası C3262 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3262
dev_langs:
- C++
helpviewer_keywords:
- C3262
ms.assetid: 3e74b9aa-de3c-4492-9331-ee73012b958b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 928ab2f6d12abb757d904417d28bd86e25be94a2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115879"
---
# <a name="compiler-error-c3262"></a>Derleyici Hatası C3262

Geçersiz dizi dizini oluşturma: Belirtilen '#' için '#' boyut-boyutlu 'dizi türü'

Yanlış simgeli dizi. Dizin sayısı dizideki boyutların sayısı ile eşleşmeyebilir.

Aşağıdaki örnek, C3262 oluşturur:

```
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
