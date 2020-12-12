---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3231'
title: Derleyici hatası C3231
ms.date: 11/04/2016
f1_keywords:
- C3231
helpviewer_keywords:
- C3231
ms.assetid: fe5dc352-e634-45fa-9534-3da176294c98
ms.openlocfilehash: 4b6a89ab1c5ecefad62852d8214c8edc3c10ccb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304096"
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
