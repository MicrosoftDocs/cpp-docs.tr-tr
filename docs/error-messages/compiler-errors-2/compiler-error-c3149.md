---
title: Derleyici hatası C3149
ms.date: 11/04/2016
f1_keywords:
- C3149
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
ms.openlocfilehash: 263eb03b7a9f45458f8d8b586adc6f1cfc5805be
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745986"
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
