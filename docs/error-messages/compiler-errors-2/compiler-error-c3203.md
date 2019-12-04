---
title: Derleyici hatası C3203
ms.date: 11/04/2016
f1_keywords:
- C3203
helpviewer_keywords:
- C3203
ms.assetid: 6356770e-22c1-434c-91fe-f60b0aa23b91
ms.openlocfilehash: 1d0ed5ec717efecb9fbea4a9451836c0471522b6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738719"
---
# <a name="compiler-error-c3203"></a>Derleyici hatası C3203

' Type ': özelleştirilmemiş sınıf şablonu veya genel parametre ya da ' param ' genel parametresi için bir şablon veya genel bağımsız değişken olarak kullanılamaz; gerçek tür bekleniyor

Bir sınıf şablonuna veya genel olarak geçersiz bir bağımsız değişken geçirtiniz. Sınıf şablonu veya genel, bir türü parametre olarak bekler.

Bu hata, Visual Studio 2005 için yapılan derleyici uygunluk işinin sonucu olarak oluşturulabilir: özelleştirilmemiş bir sınıf şablonu, temel sınıf listesinde şablon bağımsız değişkeni olarak kullanılamaz. C3203 çözümlemek için, şablon türü parametrelerini, bir temel sınıf listesinde şablon parametresi olarak kullanırken şablon sınıfı adına açıkça ekleyin.

```cpp
// C3203.cpp
template< typename T >
struct X {
   void f(X) {}
};

template< typename T >
struct Y : public X<Y> {   // C3203
// try the following line instead
// struct Y : public X<Y<T> > {
   void f(Y) {}
};

int main() {
   Y<int> y;
}
```

Aşağıdaki örnek C3203 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3203_b.cpp
// compile with: /c
template <class T>
struct S1 {};

template <class T>
class C1 {};

typedef C1<S1> MyC1;   // C3203

// OK
template <template <class> class T>
class C2 {};

typedef C2<S1> MyC1;

template <class T>
class C3 {};

typedef C3<S1<int> > MyC12;
```

C3203, genel türler kullanılırken de oluşabilir:

```cpp
// C3203_c.cpp
// compile with: /clr /c
generic <class T>
value struct GS1 {};

generic <class T>
value struct GC1 {};

typedef GC1<GS1> MyGC1;   // C3203
typedef GC1<GS1<int> > MyGC2;   // OK
```
