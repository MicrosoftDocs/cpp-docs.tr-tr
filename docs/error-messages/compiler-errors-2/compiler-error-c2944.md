---
title: Derleyici hatası C2944
ms.date: 11/04/2016
f1_keywords:
- C2944
helpviewer_keywords:
- C2944
ms.assetid: f209e668-e72f-442a-a438-8c4ff43a404a
ms.openlocfilehash: 542f7def550632a29fcb7ae28825b32b8c26f17d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755388"
---
# <a name="compiler-error-c2944"></a>Derleyici hatası C2944

' class ': tür sınıfı kimliği bir şablonun değer bağımsız değişkeni olarak yeniden tanımlandı

Şablon değeri bağımsız değişkeni olarak bir sembol yerine genel veya şablon sınıfı kullanamazsınız.

Aşağıdaki örnek C2944 oluşturur:

```cpp
// C2944.cpp
// compile with: /c
template<class T>
class TC { };

template <int TC<int> > struct X1 { };   // C2944

template <class T > struct X2 {};
```

C2944, genel türler kullanılırken de oluşabilir:

```cpp
// C2944b.cpp
// compile with: /clr /c
generic<class T>
ref class GC {};

template <int GC<int> > struct X2 { };   // C2944
template <class T> struct X3 {};   // OK
```
