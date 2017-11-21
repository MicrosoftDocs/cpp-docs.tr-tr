---
title: "Derleyici Uyarısı (düzey 4) C4706 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4706
dev_langs: C++
helpviewer_keywords: C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b128a60ce35bc6ec7cce7e10c257fe63d926fa46
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4706"></a>Derleyici Uyarısı (düzey 4) C4706
Koşullu ifade içinde ataması  
  
 Koşullu ifade test değerinde atama sonucu oluştu.  
  
 Atama yasal bir test ifadesi dahil olmak üzere başka bir ifadede kullanılan bir değeri (atamasını sol tarafındaki) vardır.  
  
 Aşağıdaki örnek C4706 oluşturur:  
  
```  
// C4706a.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a  = b ) // C4706  
   {  
   }  
}  
```  
  
 Test durumu parantezler çift olsa bile uyarı ortaya çıkar:  
  
```  
// C4706b.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a  =  b ) ) // C4706  
   {  
   }  
}  
```  
  
 Bir ilişki test ve atamanın yapmamak için kullanmak istiyorsanız `==` işleci. Örneğin, aşağıdaki testleri olup satır bir ve b eşit:  
  
```  
// C4706c.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a == b )  
   {  
   }  
}  
```  
  
 Atama sonucu değer test yapmak istiyorsanız, atama sıfır ya da null olduğundan emin olmak için test edin. Örneğin, aşağıdaki kod bu uyarı oluşturmaz:  
  
```  
// C4706d.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a = b ) != 0 )  
   {  
   }  
}  
```