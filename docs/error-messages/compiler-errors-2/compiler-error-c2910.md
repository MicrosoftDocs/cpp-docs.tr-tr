---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2910'
title: Derleyici hatası C2910
ms.date: 11/04/2016
f1_keywords:
- C2910
helpviewer_keywords:
- C2910
ms.assetid: 09c50e6a-e099-42f6-8ed6-d80e292a7a36
ms.openlocfilehash: d4bb87b054f28e0eab5bc1eef815fd1770d45809
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270634"
---
# <a name="compiler-error-c2910"></a>Derleyici hatası C2910

' function ': açık olarak özelleştirilemez

Derleyici bir işlevi bir kez açıkça özelleştirme girişimi algıladı.

Aşağıdaki örnek C2910 oluşturur:

```cpp
// C2910.cpp
// compile with: /c
template <class T>
struct S;

template <> struct S<int> { void f() {} };
template <> void S<int>::f() {}   // C2910 delete this specialization
```

Şablon olmayan bir üyeyi açıkça özelleşmenize çalışırsanız, C2910 de oluşturulabilir. Diğer bir deyişle, yalnızca bir işlev şablonunu açıkça özelleştirebilirsiniz.

Aşağıdaki örnek C2910 oluşturur:

```cpp
// C2910b.cpp
// compile with: /c
template <class T> struct A {
   A(T* p);
};

template <> struct A<void> {
   A(void* p);
};

template <class T>
inline A<T>::A(T* p) {}

template <> A<void>::A(void* p){}   // C2910
// try the following line instead
// A<void>::A(void* p){}
```

Bu hata, Visual Studio .NET 2003: ' de yapılan derleyicinin uyumluluk işinin bir sonucu olarak da oluşturulacaktır.

Visual Studio .NET 2003 ve Visual Studio .NET sürümlerinde Visual C++, kaldırma için geçerli olacak `template <>` .

Aşağıdaki örnek C2910 oluşturur:

```cpp
// C2910c.cpp
// compile with: /c
template <class T> class A {
   void f();
};

template <> class A<int> {
   void f();
};

template <> void A<int>::f() {}   // C2910
// try the following line instead
// void A<int>::f(){}   // OK
```
