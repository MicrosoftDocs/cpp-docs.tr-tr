---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2944'
title: Derleyici hatası C2944
ms.date: 11/04/2016
f1_keywords:
- C2944
helpviewer_keywords:
- C2944
ms.assetid: f209e668-e72f-442a-a438-8c4ff43a404a
ms.openlocfilehash: a25b7da5f2a3a4320b4e85dfc3bd71626795a4d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249561"
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
