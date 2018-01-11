---
title: "Derleyici Uyarısı (düzey 1) C4927 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4927
dev_langs: C++
helpviewer_keywords: C4927
ms.assetid: 7009e740-a2ef-4130-96ba-482e092f717a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 04710f4dc3c7ec011a97dd84e5616f8353b05385
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4927"></a>Derleyici Uyarısı (düzey 1) C4927
Geçersiz dönüştürme; birden fazla kullanıcı tanımlı dönüştürme örtük olarak uygulanan  
  
 Birden fazla kullanıcı tanımlı dönüştürme için tek bir değer--örtük olarak uygulanan derleyici açık bir dönüşüm bulunamadı ancak kullanılan bir dönüştürme buldunuz.  
  
 Aşağıdaki örnek C4927 oluşturur:  
  
```  
// C4927.cpp  
// compile with: /W1  
struct B  
{  
   operator int ()  
   {  
      return 0;  
   }  
};  
  
struct A  
{  
   A(int i)  
   {  
   }  
  
   /*  
   // uncomment this constructor to resolve  
   A(B b)  
   {  
   }  
   */  
};  
  
A f1( B& b)  
{  
   return A(b);  
}  
  
B& f2( B& b)  
{  
   return b;  
}  
  
A f()  
{  
   B b;  
   return A(b);   // ok  
   return f1(b);  // ok  
   return b;      // C4927  
   return B(b);   // C4927  
   return f2(b);  // C4927  
}  
  
int main()  
{  
   B b;  
   A a = b;  
   A a2(b);  
}  
```