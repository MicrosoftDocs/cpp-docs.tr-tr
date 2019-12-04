---
title: Derleyici hatası C2587
ms.date: 11/04/2016
f1_keywords:
- C2587
helpviewer_keywords:
- C2587
ms.assetid: 7637a2c7-35d4-4b5a-a8f2-515a7bda98fd
ms.openlocfilehash: 5db305ab02d2724542fb2619f1c0b7e910eb5892
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748573"
---
# <a name="compiler-error-c2587"></a>Derleyici hatası C2587

' tanımlayıcı ': yerel değişkenin varsayılan parametre olarak kullanımı geçersiz

Yerel değişkenlere varsayılan parametreler olarak izin verilmez.

Aşağıdaki örnek C2587 oluşturur:

```cpp
// C2587.cpp
// compile with: /c
int i;
void func() {
   int j;
   extern void func2( int k = j );  // C2587 -- local variable
   extern void func3( int k = i );   // OK
}
```
