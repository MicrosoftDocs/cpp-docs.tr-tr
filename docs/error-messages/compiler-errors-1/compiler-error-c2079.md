---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2079'
title: Derleyici hatası C2079
ms.date: 11/04/2016
f1_keywords:
- C2079
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
ms.openlocfilehash: 73ca5d334ac3bf3157b61a1b2a9489282ae1fe00
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151222"
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
