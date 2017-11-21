---
title: "Derleyici Hatası C2477 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2477
dev_langs: C++
helpviewer_keywords: C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 72b83b09ec97a2e7e68b2ee28429eeb31567178c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2477"></a>Derleyici Hatası C2477
'member': statik veri üyesi türetilmiş sınıf başlatılamıyor  
  
 Statik veri üyesi bir şablon sınıfı yanlış başlatıldı. ISO C++ Standart uygun için Visual Studio .NET 2003 önce Visual C++ Derleyici sürümleriyle önemli bir değişiklik budur.  
  
 Aşağıdaki örnek C2477 oluşturur:  
  
```  
// C2477.cpp  
// compile with: /Za /c  
template <class T>  
struct S {  
   static int n;  
};  
  
struct X {};  
struct A: S<X> {};  
  
int A::n = 0;   // C2477  
  
template<>  
int S<X>::n = 0;  
```