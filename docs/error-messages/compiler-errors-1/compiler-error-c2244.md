---
title: Derleyici Hatası C2244 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2244
dev_langs:
- C++
helpviewer_keywords:
- C2244
ms.assetid: d9911c12-ceb5-4f93-ac47-b44a485215c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b8c812b2443bdfada71dbb99dbceddb9074c02b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061558"
---
# <a name="compiler-error-c2244"></a>Derleyici Hatası C2244

'identifier': işlev tanımı varolan bir bildirimler eşleştirilemiyor

Olağan dışı bir kullanım birli + işleci, parantez yoktu bir işlev çağrısının önünde kullanıldı.

Bu hata, yalnızca C++ projelerinde oluşur.

Aşağıdaki örnek C2244 oluşturur:

```
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

Bir sınıf şablonunun bir üye işlev için yanlış işlev imzası kullanıldığında C2244 da meydana gelebilir.

```
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

Bir hatalı işlev imzası bir üye işlevi şablonu için kullanıldığında C2244 da meydana gelebilir.

```
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

Bir işlev şablonu kısmen özelleştirilemiyor.

```
// C2244d.cpp
template<class T, class U>
class QRS {
   void func(T t, U u);
};

template<class T>
void QRS<T,int>::func(T t, int u) {}   // C2244
```