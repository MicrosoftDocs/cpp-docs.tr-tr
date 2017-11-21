---
title: "Derleyici Hatası C3200 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3200
dev_langs: C++
helpviewer_keywords: C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e4e1df5fb5c3da260ec5eba75d25e74207fbf8e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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