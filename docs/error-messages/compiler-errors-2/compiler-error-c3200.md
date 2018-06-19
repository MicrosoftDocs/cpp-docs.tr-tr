---
title: Derleyici Hatası C3200 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3200
dev_langs:
- C++
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6aa34ea006b06138290417387bd393589b630aa4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251313"
---
# <a name="compiler-error-c3200"></a>Derleyici Hatası C3200
'şablon': 'parametresi' şablon parametresi için geçersiz şablon bağımsız değişken beklenen bir sınıf şablonu  
  
 Sınıf şablonu için geçersiz bağımsız değişken geçirildi. Sınıf şablonu şablon bir parametre bekler. Aşağıdaki örnekte, çağırma `Y<int, int> aY` C3200 oluşturur. İlk parametre gibi bir şablon olması gereken `Y<X, int> aY`.  
  
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