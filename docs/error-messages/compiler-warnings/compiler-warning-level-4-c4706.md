---
title: Derleyici Uyarısı (düzey 4) C4706 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4706
dev_langs:
- C++
helpviewer_keywords:
- C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1131147a9600525746cb3e89119189ed9e5026a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296975"
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