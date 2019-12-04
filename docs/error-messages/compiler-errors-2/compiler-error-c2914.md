---
title: Derleyici hatası C2914
ms.date: 11/04/2016
f1_keywords:
- C2914
helpviewer_keywords:
- C2914
ms.assetid: fc6a0592-f53e-4f5a-88cb-780bbed4acf2
ms.openlocfilehash: bed9e31d7d1de069ee708f8f482d26b37bc16833
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761064"
---
# <a name="compiler-error-c2914"></a>Derleyici hatası C2914

' tanımlayıcı ': işlev bağımsız değişkeni belirsiz olduğundan tür bağımsız değişkeni çıkarılamıyor

Derleyici, genel veya şablon bağımsız değişkeni için kullanılacak aşırı yüklenmiş işlevleri belirleyemez.

Aşağıdaki örnek C2914 oluşturur:

```cpp
// C2914.cpp
// compile with: /c
void f(int);
void f(double);
template<class T> void g(void (*) (T));
void h() { g(f); }   // C2914
// try the following line instead
// void h() { g<int>(f); }
```

C2914, genel türler kullanılırken de oluşabilir.  Aşağıdaki örnek C2914 oluşturur:

```cpp
// C2914b.cpp
// compile with: /clr /c
void f(int);
void f(double);

template<class T>
void gf(void (*) (T));

void h() { gf(f);}   // C2914
// try the following line instead
void h() { gf<int>(f); }
```
