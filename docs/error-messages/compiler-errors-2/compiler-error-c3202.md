---
title: "Derleyici Hatası C3202 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3202
dev_langs: C++
helpviewer_keywords: C3202
ms.assetid: 23528a0c-5493-4804-9789-cd3c38e49fb9
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 60e0432a40b7aa66762c235223b0f8d48a50bab4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3202"></a>Derleyici Hatası C3202
'arg name': 'parametresi' şablon parametresi için geçersiz varsayılan bağımsız değişken beklenen bir sınıf şablonu  
  
 Şablon parametresi için geçersiz varsayılan bağımsız değişken geçirildi.  
  
 Aşağıdaki örnek C3202 oluşturur:  
  
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