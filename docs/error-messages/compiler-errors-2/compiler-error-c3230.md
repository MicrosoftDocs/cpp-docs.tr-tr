---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3230'
title: Derleyici hatası C3230
ms.date: 11/04/2016
f1_keywords:
- C3230
helpviewer_keywords:
- C3230
ms.assetid: 5ec53f25-59f6-4801-81e7-7b68bf04994d
ms.openlocfilehash: dfd14d11b18c7398ef5881ebe8935e0cf6c302cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272420"
---
# <a name="compiler-error-c3230"></a>Derleyici hatası C3230

' function ': ' Template ' için şablon türü bağımsız değişkeni genel bir tür parametresi içeremez: ' param '

Şablonlar derleme zamanında oluşturulur, ancak genel türler çalışma zamanında oluşturulur. Bu nedenle, genel tür son olarak bilindiğinde şablon çalışma zamanında örneklenemez, ancak şablonu çağırabildiği genel kodu oluşturmak mümkün değildir.

Aşağıdaki örnek C3230 oluşturur:

```cpp
// C3230.cpp
// compile with: /clr /LD
template <class S>
void f(S t);

generic <class U>
ref class C {
   void f1(U x) {
      f(x);   // C3230
   }
};
```
