---
title: Derleyici Hatası C2079
ms.date: 11/04/2016
f1_keywords:
- C2079
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
ms.openlocfilehash: 68435610680e3b21415a1d9439a8133fd1e2557f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621669"
---
# <a name="compiler-error-c2079"></a>Derleyici Hatası C2079

'identifier' tanımsız sınıf/yapı/birleşim 'name' kullanır.

Belirtilen bir tanımsız sınıf, yapı veya birleşim tanımlayıcısıdır.

Bu hata anonim birleşim başlatarak neden olabilir.

Aşağıdaki örnek, C2079 oluşturur:

```
// C2079.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   std::ifstream g;   // C2079
}
```

Olası çözüm:

```
// C2079b.cpp
// compile with: /EHsc
#include <fstream>
int main( ) {
   std::ifstream g;
}
```

Yığında olan ileri dönük bildirimi kapsam içinde olan bir türü bir nesneyi bildirmek çalışırsanız C2079 da meydana gelebilir.

```
// C2079c.cpp
class A;

class B {
   A a;   // C2079
};

class A {};
```

Olası çözüm:

```
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