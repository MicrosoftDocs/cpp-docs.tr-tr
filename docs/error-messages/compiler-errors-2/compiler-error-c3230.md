---
title: Derleyici Hatası C3230
ms.date: 11/04/2016
f1_keywords:
- C3230
helpviewer_keywords:
- C3230
ms.assetid: 5ec53f25-59f6-4801-81e7-7b68bf04994d
ms.openlocfilehash: a4d5edeb5898a57b99839b7e044f909cea1ec199
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173892"
---
# <a name="compiler-error-c3230"></a>Derleyici Hatası C3230

'function': şablon türü bağımsız değişkeni için 'şablon' genel tür parametresi içeremez: 'param'

Şablon, derleme zamanında örneği oluşturulur, ancak genel türler çalışma zamanında örneği oluşturulur. Bu nedenle, genel tür son olarak bilinen, çalışma zamanında şablonu başlatılamaz çünkü şablon çağırabilirsiniz genel kod üretmek mümkün değildir.

Aşağıdaki örnek, C3230 oluşturur:

```
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