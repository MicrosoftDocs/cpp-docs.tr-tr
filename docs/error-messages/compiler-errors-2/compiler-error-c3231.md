---
title: Derleyici Hatası C3231
ms.date: 11/04/2016
f1_keywords:
- C3231
helpviewer_keywords:
- C3231
ms.assetid: fe5dc352-e634-45fa-9534-3da176294c98
ms.openlocfilehash: 653f0b18737f937483f5d3e79cb99c9a55160c19
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173863"
---
# <a name="compiler-error-c3231"></a>Derleyici Hatası C3231

'değişken': şablon türü bağımsız değişkeni, genel tür parametresi kullanamaz

Şablon, derleme zamanında örneği oluşturulur, ancak genel türler çalışma zamanında örneği oluşturulur. Bu nedenle, genel tür son olarak bilinen, çalışma zamanında şablonu başlatılamaz çünkü şablon çağırabilirsiniz genel kod üretmek mümkün değildir.

Aşağıdaki örnek, C3231 oluşturur:

```
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