---
title: Derleyici Hatası C2477
ms.date: 11/04/2016
f1_keywords:
- C2477
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
ms.openlocfilehash: 73d8daa9576e4edc29958918c107e9edf18cc579
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447963"
---
# <a name="compiler-error-c2477"></a>Derleyici Hatası C2477

'member': statik veri üyesi türetilmiş sınıf aracılığıyla başlatılamaz

Bir şablon sınıfının statik veri üyesine hatalı olarak başlatıldı. Bu sürümler Microsoft ile bir değişiklik, C++ 2003'ten önceki Visual Studio .NET ISO uymak için derleyici C++ standart.

Aşağıdaki örnek, C2477 oluşturur:

```
// C2477.cpp
// compile with: /Za /c
template <class T>
struct S {
   static int n;
};

struct X {};
struct A: S<X> {};

int A::n = 0;   // C2477

template<>
int S<X>::n = 0;
```