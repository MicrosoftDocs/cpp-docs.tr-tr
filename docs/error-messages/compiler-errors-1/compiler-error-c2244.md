---
title: Derleyici hatası C2244
ms.date: 11/04/2016
f1_keywords:
- C2244
helpviewer_keywords:
- C2244
ms.assetid: d9911c12-ceb5-4f93-ac47-b44a485215c2
ms.openlocfilehash: 97ff469c6f3f766bd1b5412133003bae2acaddfc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759483"
---
# <a name="compiler-error-c2244"></a>Derleyici hatası C2244

' tanımlayıcı ': işlev tanımı varolan bir bildirimle eşleştirilemiyor

Birli + işlecinin alışılmadık kullanımı parantez olmayan bir işlev çağrısının önünde kullanıldı.

Bu hata yalnızca C++ projelerde oluşur.

Aşağıdaki örnek C2244 oluşturur:

```cpp
// C2244.cpp
int func(char) {
   return 0;
}

int func(int) {
   return 0;
}

int main() {
   +func;   // C2244
}
```

Ayrıca, bir sınıf şablonunun üye işlevi için yanlış bir işlev imzası kullanıldığında C2244 de oluşabilir.

```cpp
// C2244b.cpp
// compile with: /c
template<class T>
class XYZ {
   void func(T t);
};

template<class T>
void XYZ<T>::func(int i) {}   // C2244 wrong function signature
// try the following line instead
// void XYZ<T>::func(T t) {}
```

C2244, bir üye işlev şablonu için yanlış bir işlev imzası kullanıldığında da oluşabilir.

```cpp
// C2244c.cpp
// compile with: /c
class ABC {
   template<class T>
   void func(int i, T t);
};

template<class T>
void ABC::func(int i) {}   // C2244 wrong signature
// try the following line instead
// void ABC::func(int i, T t) {}
```

Bir işlev şablonunu kısmen özelleştirilemez.

```cpp
// C2244d.cpp
template<class T, class U>
class QRS {
   void func(T t, U u);
};

template<class T>
void QRS<T,int>::func(T t, int u) {}   // C2244
```
