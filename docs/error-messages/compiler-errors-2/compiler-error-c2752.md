---
title: Derleyici Hatası C2752
ms.date: 11/04/2016
f1_keywords:
- C2752
helpviewer_keywords:
- C2752
ms.assetid: ae42b3ec-84a9-4e9d-8d59-3d208132d0b2
ms.openlocfilehash: cecc1433a80bdbdcc79eb9e5493486498a820e40
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622904"
---
# <a name="compiler-error-c2752"></a>Derleyici Hatası C2752

'şablon': şablon bağımsız değişken listesiyle birden fazla kısmi özelleştirme eşleşiyor

Örneklemesi belirsiz.

Aşağıdaki örnek, C2752 oluşturur:

```
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