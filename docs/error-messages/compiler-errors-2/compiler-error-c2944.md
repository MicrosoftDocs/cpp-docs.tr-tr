---
title: Derleyici Hatası C2944
ms.date: 11/04/2016
f1_keywords:
- C2944
helpviewer_keywords:
- C2944
ms.assetid: f209e668-e72f-442a-a438-8c4ff43a404a
ms.openlocfilehash: bed23b7d9117d1d1acad80f4f3d81e8b0b9d0252
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652211"
---
# <a name="compiler-error-c2944"></a>Derleyici Hatası C2944

'class': türü sınıf kimliği için bir şablon bir değeri bağımsız değişken olarak yeniden tanımlandı

Genel veya Şablon sınıfı bir şablon değeri bağımsız değişkeni bir simge yerine kullanamazsınız.

Aşağıdaki örnek, C2944 oluşturur:

```
// C2944.cpp
// compile with: /c
template<class T>
class TC { };

template <int TC<int> > struct X1 { };   // C2944

template <class T > struct X2 {};
```

C2944, genel türler kullanırken da meydana gelebilir:

```
// C2944b.cpp
// compile with: /clr /c
generic<class T>
ref class GC {};

template <int GC<int> > struct X2 { };   // C2944
template <class T> struct X3 {};   // OK
```