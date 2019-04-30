---
title: Derleyici Hatası C3203
ms.date: 11/04/2016
f1_keywords:
- C3203
helpviewer_keywords:
- C3203
ms.assetid: 6356770e-22c1-434c-91fe-f60b0aa23b91
ms.openlocfilehash: 65b7e1d8f03b5e59bd21091531bc9d21472e4ae4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402742"
---
# <a name="compiler-error-c3203"></a>Derleyici Hatası C3203

'type': uzmanlaşmamış sınıf şablonunun veya genel şablon veya şablon ya da genel parametre 'param' için genel bağımsız değişken olarak kullanılamaz; gerçek tür bekleniyor

Bir sınıf şablonunun veya genel geçersiz bağımsız değişken geçirildi. Sınıf şablonu veya genel bir tür bir parametre bekliyor.

Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucu olarak oluşturulan: uzmanlaşmamış sınıf şablonu, bir taban sınıfı listesinde şablon bağımsız değişkeni olarak kullanılamaz. C3203 çözmek için açıkça şablonu tür parametrelerinin şablon sınıf adı için bir taban sınıfı listesinde bir şablon parametresi olarak kullanılırken ekleyin.

```
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

Aşağıdaki örnek, C3203 oluşturur ve bu sorunun nasıl gösterir:

```
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

C3203, genel türler kullanırken da meydana gelebilir:

```
// C3203_c.cpp
// compile with: /clr /c
generic <class T>
value struct GS1 {};

generic <class T>
value struct GC1 {};

typedef GC1<GS1> MyGC1;   // C3203
typedef GC1<GS1<int> > MyGC2;   // OK
```