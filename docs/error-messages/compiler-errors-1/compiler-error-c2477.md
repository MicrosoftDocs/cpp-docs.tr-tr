---
title: Derleyici Hatası C2477
ms.date: 11/04/2016
f1_keywords:
- C2477
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
ms.openlocfilehash: 27db194cb308d711a259127b628c60b4d10b94ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383236"
---
# <a name="compiler-error-c2477"></a>Derleyici Hatası C2477

'member': statik veri üyesi türetilmiş sınıf aracılığıyla başlatılamaz

Bir şablon sınıfının statik veri üyesine hatalı olarak başlatıldı. ISO C++ standardı uymak için bir Visual Studio .NET 2003 önce Visual C++ Derleyici sürümleri ile değişiklik budur.

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