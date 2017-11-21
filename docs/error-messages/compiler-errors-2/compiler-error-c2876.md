---
title: "Derleyici Hatası C2876 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2876
dev_langs: C++
helpviewer_keywords: C2876
ms.assetid: 8b674bf1-f9f4-4a8e-8127-e884c1d1708f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 84b5609dab6e8f12c5545c2e5c8d64a173cd41ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2876"></a>Derleyici Hatası C2876
'class::symbol': tüm aşırı erişilebilir  
  
 Bir işlevin bir taban sınıf içinde tüm aşırı yüklenmiş formları türetilmiş sınıf erişilebilir olması gerekir.  
  
 Aşağıdaki örnek C2876 oluşturur:  
  
```  
// C2876.cpp  
// compile with: /c  
class A {  
public:     
   double a(double);  
private:  
   int a(int);  
};  
  
class B : public A {  
   using A::a;   // C2876 one overload is private in base class  
};  
```