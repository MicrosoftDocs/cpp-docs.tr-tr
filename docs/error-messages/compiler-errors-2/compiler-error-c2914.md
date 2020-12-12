---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2914'
title: Derleyici hatası C2914
ms.date: 11/04/2016
f1_keywords:
- C2914
helpviewer_keywords:
- C2914
ms.assetid: fc6a0592-f53e-4f5a-88cb-780bbed4acf2
ms.openlocfilehash: 7ff40982a8c6d93130265795fa334dbbc9c21cc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270452"
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
