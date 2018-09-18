---
title: Derleyici Hatası C3202 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3202
dev_langs:
- C++
helpviewer_keywords:
- C3202
ms.assetid: 23528a0c-5493-4804-9789-cd3c38e49fb9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 254843386943b677be6df2c1ab7f1da56265e1d8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070333"
---
# <a name="compiler-error-c3202"></a>Derleyici Hatası C3202

'değişken adı': şablon parametresi 'parametresi' için geçersiz varsayılan bağımsız değişken; sınıf şablonu bekleniyor

Bir şablon parametresi için geçersiz varsayılan bağımsız değişken geçirildi.

Aşağıdaki örnek, C3202 oluşturur:

```
// C3202.cpp
template<typename T>
class X
{
};

class Z
{
};

template<template<typename U> class T1 = Z, typename T2> // C3202
class Y
{
};
```