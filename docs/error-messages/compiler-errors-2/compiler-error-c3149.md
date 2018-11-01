---
title: Derleyici Hatası C3149
ms.date: 11/04/2016
f1_keywords:
- C3149
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
ms.openlocfilehash: 8238dcec821256dad8101cd7ad59b2d85882c218
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622878"
---
# <a name="compiler-error-c3149"></a>Derleyici Hatası C3149

'type': bir üst düzey 'char' olmadan bu tür burada kullanılamaz

Bir bildirimi düzgün belirtilmedi.

Örneğin, bir CLR türü genel kapsamda tanımlanan olabilir ve tanımının bir parçası türünde bir değişken oluşturmak denemiş olabilirsiniz. CLR türlerinin genel değişkenlere izin verilmiyor çünkü derleyici C3149 oluşturur.

Bu hatayı gidermek için bir işlev veya tür tanımındaki CLR türlerinin değişkenleri bildirin.

Aşağıdaki örnek, C3149 oluşturur:

```
// C3149.cpp
// compile with: /clr
using namespace System;
int main() {
   // declare an array of value types
   array< Int32 ^> IntArray;   // C3149
   array< Int32>^ IntArray2;   // OK
}
```

Aşağıdaki örnek, C3149 oluşturur:

```
// C3149b.cpp
// compile with: /clr /c
delegate int MyDelegate(const int, int);
void Test1(MyDelegate m) {}   // C3149
void Test2(MyDelegate ^ m) {}   // OK
```
