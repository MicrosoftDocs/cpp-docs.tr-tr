---
title: Derleyici Hatası C3203 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3203
dev_langs:
- C++
helpviewer_keywords:
- C3203
ms.assetid: 6356770e-22c1-434c-91fe-f60b0aa23b91
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae0707bc56a812af77d30ac9dac8e945ee5e2aa6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082864"
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