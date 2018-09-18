---
title: Derleyici Hatası C3201 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3201
dev_langs:
- C++
helpviewer_keywords:
- C3201
ms.assetid: ec19cd64-1789-40a3-b2db-dff2852b9d98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 466899de89e1f8760ec78e7d346ef949fab667be
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074259"
---
# <a name="compiler-error-c3201"></a>Derleyici Hatası C3201

'şablon' sınıf şablonunun şablon parametre listesi 'şablon' şablon parametresinin şablon parametre listesiyle eşleşmiyor

Bir sınıf şablonunun bir sınıf şablonunun şablon parametre almayan bağımsız değişken geçirilen veya eşleşmeyen birkaç varsayılan şablon bağımsız değişkeni için şablon bağımsız değişkenleri geçirildi.

```
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