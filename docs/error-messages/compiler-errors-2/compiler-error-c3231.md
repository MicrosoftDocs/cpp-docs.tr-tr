---
title: Derleyici hatası C3231
ms.date: 11/04/2016
f1_keywords:
- C3231
helpviewer_keywords:
- C3231
ms.assetid: fe5dc352-e634-45fa-9534-3da176294c98
ms.openlocfilehash: 3bc8293f0cbed7c2093cfe9dd0513b690b8c76f0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750344"
---
# <a name="compiler-error-c3231"></a>Derleyici hatası C3231

' arg ': şablon türü bağımsız değişkeni genel bir tür parametresi kullanamaz

Şablonlar derleme zamanında oluşturulur, ancak genel türler çalışma zamanında oluşturulur. Bu nedenle, genel tür son olarak bilindiğinde şablon çalışma zamanında örneklenemez, ancak şablonu çağırabildiği genel kodu oluşturmak mümkün değildir.

Aşağıdaki örnek C3231 oluşturur:

```cpp
// C3231.cpp
// compile with: /clr /LD
template <class T> class A;

generic <class T>
ref class C {
   void f() {
      A<T> a;   // C3231
   }
};
```
