---
title: Derleyici hatası C3200
ms.date: 11/04/2016
f1_keywords:
- C3200
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
ms.openlocfilehash: 7f6b514231bcda18404e891e0acbe457c8f95146
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738784"
---
# <a name="compiler-error-c3200"></a>Derleyici hatası C3200

' Template ': şablon parametresi ' Parameter ' için geçersiz şablon bağımsız değişkeni, bir sınıf şablonu bekleniyor

Bir sınıf şablonuna geçersiz bir bağımsız değişken geçirtiniz. Sınıf şablonu, şablonu bir parametre olarak bekler. Aşağıdaki örnekte `Y<int, int> aY` çağrısı, C3200 oluşturacaktır. İlk parametrenin `Y<X, int> aY`gibi bir şablon olması gerekir.

```cpp
// C3200.cpp
template<typename T>
class X
{
};

template<template<typename U> class T1, typename T2>
class Y
{
};

int main()
{
   Y<int, int> y;   // C3200
}
```
