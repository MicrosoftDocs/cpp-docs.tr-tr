---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2477'
title: Derleyici hatası C2477
ms.date: 11/04/2016
f1_keywords:
- C2477
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
ms.openlocfilehash: 50cbb3523e6dc30dc465876435db40a80e2768fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164399"
---
# <a name="compiler-error-c2477"></a>Derleyici hatası C2477

' üye ': statik veri üyesi türetilmiş sınıf aracılığıyla başlatılamaz

Şablon sınıfının statik veri üyesi yanlış başlatılmış. Bu, ISO C++ standardına uymak için, Visual Studio .NET 2003 ' den önceki Microsoft C++ derleyicisi sürümleriyle Son değişiklik olduğunu ortadan kaldırma.

Aşağıdaki örnek C2477 oluşturur:

```cpp
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
