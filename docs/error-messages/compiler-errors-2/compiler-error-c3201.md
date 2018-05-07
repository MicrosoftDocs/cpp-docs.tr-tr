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
ms.openlocfilehash: 51ebf253a1d1e5963ff05aa343295e133a0641c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3201"></a>Derleyici Hatası C3201
sınıf şablonu 'şablon' için şablon parametre listesi 'şablon' şablon parametresi için şablon parametre listesi eşleşmiyor.  
  
 Sınıf şablonu bağımsız değişkeninde bir şablon parametresini almayan bir sınıf şablonu geçirilen veya eşleşmeyen birkaç varsayılan şablon bağımsız değişken için şablon bağımsız değişken geçirildi.  
  
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