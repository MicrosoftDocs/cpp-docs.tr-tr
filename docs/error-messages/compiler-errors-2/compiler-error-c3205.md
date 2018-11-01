---
title: Derleyici Hatası C3205
ms.date: 11/04/2016
f1_keywords:
- C3205
helpviewer_keywords:
- C3205
ms.assetid: 802d306e-5ff3-4491-8a22-c5f1c072d005
ms.openlocfilehash: bd4d17ff2b6a0197db730a53c5846806335c9fd7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577521"
---
# <a name="compiler-error-c3205"></a>Derleyici Hatası C3205

'parameter' şablon parametresi için bağımsız değişken listesi eksik

A [şablon](../../cpp/templates-cpp.md) parametresi eksik.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3205 oluşturur:

```cpp
// C3205.cpp
template<template<class> class T> struct A {
   typedef T unparameterized_type;   // C3205
   // try the following line instead
   // typedef T<int> unparameterized_type;
};

template <class T>
struct B {
   typedef int value_type;
};

int main() {
   A<B> x;
}
```