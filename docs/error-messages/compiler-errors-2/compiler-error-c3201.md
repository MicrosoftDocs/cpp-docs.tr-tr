---
title: Derleyici hatası C3201
ms.date: 11/04/2016
f1_keywords:
- C3201
helpviewer_keywords:
- C3201
ms.assetid: ec19cd64-1789-40a3-b2db-dff2852b9d98
ms.openlocfilehash: 4da6616c59ea4b8a720c8e2dc9742e37a9939171
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738771"
---
# <a name="compiler-error-c3201"></a>Derleyici hatası C3201

' Template ' sınıf şablonunun şablon parametre listesi, ' Template ' şablon parametresinin şablon parametre listesiyle eşleşmiyor

Bağımsız değişkende bir sınıf şablonunu, şablon parametresi olmayan bir sınıf şablonuna geçirtiniz veya varsayılan şablon bağımsız değişkeni için eşleşmeyen sayıda şablon bağımsız değişkeni geçirtiniz.

```cpp
// C3201.cpp
template<typename T1, typename T2>
class X1
{
};

template<template<typename T> class U = X1>   // C3201
class X2
{
};

template<template<typename T, typename V> class U = X1>   // OK
class X3
{
};
```
