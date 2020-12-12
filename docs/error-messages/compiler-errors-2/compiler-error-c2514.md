---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2514'
title: Derleyici hatası C2514
ms.date: 11/04/2016
f1_keywords:
- C2514
helpviewer_keywords:
- C2514
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
ms.openlocfilehash: 3999a5a65df08142b68e7257b257d39d1b5245e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212824"
---
# <a name="compiler-error-c2514"></a>Derleyici hatası C2514

' class ': sınıfta Oluşturucu yok

Sınıf, yapı veya Union içinde, örneğini oluşturmak için kullanılan parametrelerle eşleşen bir parametre listesi olan bir Oluşturucu yok.

Sınıf, örnekedilmeden önce tam olarak bildirilmelidir.

Aşağıdaki örnek C2514 oluşturur:

```cpp
// C2514.cpp
// compile with: /c
class f;

class g {
public:
    g (int x);
};

class fmaker {
   f *func1() {
      return new f(2);   // C2514
   }

   g *func2() {
      return new g(2);   // OK
   }
};
```
