---
title: Derleyici hatası C2079
ms.date: 11/04/2016
f1_keywords:
- C2079
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
ms.openlocfilehash: ea158d8dada013f6b90d0fbe1e7502665c1c24da
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757728"
---
# <a name="compiler-error-c2079"></a>Derleyici hatası C2079

' Identifier ' tanımlanmamış Class/struct/Union ' name ' kullanır

Belirtilen tanımlayıcı tanımlanmamış bir sınıf, yapı veya birleşim.

Bu hata, anonim bir birleşim başlatılmasına neden olabilir.

Aşağıdaki örnek C2079 oluşturur:

```cpp
// C2079.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   std::ifstream g;   // C2079
}
```

Olası çözüm:

```cpp
// C2079b.cpp
// compile with: /EHsc
#include <fstream>
int main( ) {
   std::ifstream g;
}
```

C2079, ileri bildirimi yalnızca kapsam içinde olan bir türün yığınında bir nesne bildirmeye çalışırsanız da oluşabilir.

```cpp
// C2079c.cpp
class A;

class B {
   A a;   // C2079
};

class A {};
```

Olası çözüm:

```cpp
// C2079d.cpp
// compile with: /c
class A;
class C {};

class B {
   A * a;
   C c;
};

class A {};
```
