---
title: "Derleyici Hatası C2073 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2073
dev_langs: C++
helpviewer_keywords: C2073
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2503073e960f93cbede95bf54d2d4d1bd079c185
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2073"></a>Derleyici Hatası C2073
'tanımlayıcısı': kısmen başlatılmış dizinin öğeleri, bir varsayılan oluşturucusu olmalıdır  
  
 Çok az başlatıcıları için kullanıcı tanımlı türler veya sabit bir dizi belirtildi. Açık bir başlatıcı ve karşılık gelen kurucusu bir dizi üyesi için belirtilmezse, varsayılan bir oluşturucu sağlanmalıdır.  
  
 Aşağıdaki örnek C2073 oluşturur:  
  
```  
// C2073.cpp  
class A {  
public:  
   A( int );   // constructor for ints only  
};  
A a[3] = { A(1), A(2) };   // C2073, no default constructor  
```  
  
```  
// C2073b.cpp  
// compile with: /c  
class B {  
public:  
   B();   // default constructor declared  
   B( int );  
};  
B b[3] = { B(1), B(2) };   // OK  
```