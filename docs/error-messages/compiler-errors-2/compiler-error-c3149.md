---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3149'
title: Derleyici hatası C3149
ms.date: 11/04/2016
f1_keywords:
- C3149
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
ms.openlocfilehash: 596a8d2728e7598a737da4aa5a1650df669db969
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322096"
---
# <a name="compiler-error-c3149"></a>Derleyici hatası C3149

' Type ': Bu tür, üst düzey ' Char ' olmadan burada kullanılamaz

Bir bildirim doğru bir şekilde belirtilmedi.

Örneğin, genel kapsamda bir CLR türü tanımlamış ve tanımın bir parçası olarak türde bir değişken oluşturmaya çalışmış olabilirsiniz. CLR türlerinin genel değişkenlerine izin verilmediğinden, derleyici C3149 oluşturacaktır.

Bu hatayı çözmek için bir işlev veya tür tanımı içindeki CLR türlerinin değişkenlerini bildirin.

Aşağıdaki örnek C3149 oluşturur:

```cpp
// C3149.cpp
// compile with: /clr
using namespace System;
int main() {
   // declare an array of value types
   array< Int32 ^> IntArray;   // C3149
   array< Int32>^ IntArray2;   // OK
}
```

Aşağıdaki örnek C3149 oluşturur:

```cpp
// C3149b.cpp
// compile with: /clr /c
delegate int MyDelegate(const int, int);
void Test1(MyDelegate m) {}   // C3149
void Test2(MyDelegate ^ m) {}   // OK
```
