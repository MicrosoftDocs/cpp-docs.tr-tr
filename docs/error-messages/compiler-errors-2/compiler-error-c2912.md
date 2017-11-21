---
title: "Derleyici Hatası C2912 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2912
dev_langs: C++
helpviewer_keywords: C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d19c1681274a03369987979af8c9c8a7253a5b57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2912"></a>Derleyici Hatası C2912
Açık uzmanlık 'bildirimi' işlevi şablon uzmanlaşması değil  
  
 Şablon olmayan işlevi specialize olamaz.  
  
 Aşağıdaki örnek C2912 oluşturur:  
  
```  
// C2912.cpp  
// compile with: /c  
void f(char);  
template<> void f(char);   // C2912  
template<class T> void f(T);   // OK  
```  
  
 Bu hata ayrıca Visual Studio .NET 2003'te yapıldığı derleyici uyumluluğu iş sonucu olarak oluşturulacak: her açık özelleştirmesi için birincil parametrelerinin eşleşecek şekilde açık uzmanlık parametrelerinin seçmeniz gerekir Şablon.  
  
```  
// C2912b.cpp  
class CF {  
public:  
   template <class A> CF(const A& a) {}   // primary template  
  
   // attempted explicit specialization  
   template <> CF(const char* p) {}   // C2912  
  
   // try the following line instead  
   // template <> CF(const char& p) {}  
};  
```