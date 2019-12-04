---
title: Derleyici hatası C2977
ms.date: 11/04/2016
f1_keywords:
- C2977
helpviewer_keywords:
- C2977
ms.assetid: 3c4218e0-5d03-4a2b-b757-c507c35f3542
ms.openlocfilehash: eaf314276b2fdf536c1d11c0e0752a6de396b5a8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751683"
---
# <a name="compiler-error-c2977"></a>Derleyici hatası C2977

' tanımlayıcı ': çok fazla sayıda tür bağımsız değişkeni

Genel veya şablonda çok fazla sayıda gerçek bağımsız değişken var. Doğru parametre sayısını bulmak için genel veya şablon bildirimini denetleyin.

Aşağıdaki örnek C2977 oluşturur:

```cpp
// C2977.cpp
// compile with: /c
template<class T, int i>
class MyClass {};

template MyClass< int , 1, 1 >;   // C2977
template MyClass< int , 1 >;   // OK
```

C2977, genel türler kullanılırken de oluşabilir:

```cpp
// C2977b.cpp
// compile with: /clr
// C2977 expected
generic <class T, class U>
void f(){}

generic <class T>
ref struct GC1 {};

int main() {
   // Delete the following 2 lines to resolve.
   GC1<int, char> ^ pgc1;
   f<int,int,int>();

   // OK
   GC1<int> ^ pgc1;
   f<int, int>();
}
```
