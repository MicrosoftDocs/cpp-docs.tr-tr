---
title: Derleyici Hatası C3200
ms.date: 11/04/2016
f1_keywords:
- C3200
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
ms.openlocfilehash: 7eb0c00f4f4c5c59766bf305acfef89e12a6cfb1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505072"
---
# <a name="compiler-error-c3200"></a>Derleyici Hatası C3200

'şablon': şablon parametresi 'parametresi' için geçersiz şablon bağımsız değişkeni; sınıf şablonu bekleniyor

Bir sınıf şablonu için geçersiz bağımsız değişken geçirildi. Sınıf şablonunun şablon parametre olarak bekler. Aşağıdaki örnekte, çağırma `Y<int, int> aY` C3200 oluşturur. İlk parametre, bir şablon gibi olması gereken `Y<X, int> aY`.

```
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