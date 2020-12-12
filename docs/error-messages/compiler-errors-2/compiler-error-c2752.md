---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2752'
title: Derleyici hatası C2752
ms.date: 11/04/2016
f1_keywords:
- C2752
helpviewer_keywords:
- C2752
ms.assetid: ae42b3ec-84a9-4e9d-8d59-3d208132d0b2
ms.openlocfilehash: 5a508ca9c286392bc05dd30602e138880882f813
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174435"
---
# <a name="compiler-error-c2752"></a>Derleyici hatası C2752

' Template ': şablon bağımsız değişken listesiyle birden fazla kısmi özelleştirme eşleşiyor

Örnekleme belirsizdir.

Aşağıdaki örnek C2752 oluşturur:

```cpp
// C2752.cpp
template<class T, class U>
struct A {};

template<class T, class U>
struct A<T*, U> {};

template<class T, class U>
struct A<T,U*> {};

// try the following line instead
// template<class T, class U> struct A<T*,U*> {};

int main() {
   A<char*,int*> a;   // C2752 an instantiation

   // OK
   A<char*,int> a1;
   A<char,int*> a2;
   A<char,int> a3;
}
```
