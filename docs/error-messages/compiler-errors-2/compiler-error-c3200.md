---
description: 'Daha fazla bilgi edinin: derleyici hatası C3200'
title: Derleyici hatası C3200
ms.date: 11/04/2016
f1_keywords:
- C3200
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
ms.openlocfilehash: c693878628ff0bd9dddcb2f100ca652910b0fb89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330665"
---
# <a name="compiler-error-c3200"></a>Derleyici hatası C3200

' Template ': şablon parametresi ' Parameter ' için geçersiz şablon bağımsız değişkeni, bir sınıf şablonu bekleniyor

Bir sınıf şablonuna geçersiz bir bağımsız değişken geçirtiniz. Sınıf şablonu, şablonu bir parametre olarak bekler. Aşağıdaki örnekte, çağrı `Y<int, int> aY` C3200 oluşturacaktır. İlk parametrenin gibi bir şablon olması gerekir `Y<X, int> aY` .

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
