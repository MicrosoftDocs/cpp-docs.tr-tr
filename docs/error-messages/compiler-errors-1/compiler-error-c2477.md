---
title: Derleyici Hatası C2477 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2477
dev_langs:
- C++
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca1212a664582f19e91fbf21bde36431ec715946
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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