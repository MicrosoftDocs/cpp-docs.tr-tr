---
title: Derleyici Hatası C3205 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3205
dev_langs:
- C++
helpviewer_keywords:
- C3205
ms.assetid: 802d306e-5ff3-4491-8a22-c5f1c072d005
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b47054bcddbb2d171f7ab8fadb861c065e5b1a5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109411"
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