---
title: "Derleyici Hatası C2990 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2990
dev_langs:
- C++
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94b40071e08dd22c5382e310d27c125f76e1bd6b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2990"></a>Derleyici Hatası C2990
'class': olmayan sınıf türü olarak zaten bir sınıf türü olarak bildirilmiş  
  
 Olmayan genel veya Şablon sınıfı bir genel veya Şablon sınıfı yeniden tanımlamaktadır. Üstbilgi dosyaları çakışmaları denetleyin.  
  
 Aşağıdaki örnek C2990 oluşturur:  
  
```  
// C2990.cpp  
// compile with: /c  
template <class T>  
class C{};  
class C{};   // C2990  
```  
  
 Ayrıca C2990 genel türler kullanma ortaya çıkabilir:  
  
```  
// C2990b.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC;  
  
ref struct GC {};   // C2990  
```  
  
 C2990 de Visual C++ derleyicisi sonu değişiklik nedeniyle Visual C++ 2005 oluşabilir; Derleyici artık aynı tür için birden çok bildirimleri şablon belirtimine göre aynı olmasını gerektirir.  
  
 Aşağıdaki örnek C2990 oluşturur:  
  
```  
// C2990c.cpp  
// compile with: /c  
template<class T>  
class A;  
  
template<class T>  
struct A2 {  
   friend class A;   // C2990  
};  
  
// OK  
template<class T>  
struct B {  
   template<class T>  
   friend class A;  
};  
```