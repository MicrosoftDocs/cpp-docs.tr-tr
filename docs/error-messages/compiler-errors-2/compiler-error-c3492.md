---
title: "Derleyici Hatası C3492 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3492
dev_langs: C++
helpviewer_keywords: C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cd8b70a22f24e41889c2c6d13cbb5fc2ff3e85e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3492"></a>Derleyici Hatası C3492
'var': anonim bir birleşim üyesi yakalayamazsınız  
  
 Adsız bir birleşim üyesi yakalama yapılamaz.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   UNION bir ad verin ve tam birleşim yapısı lambda ifadesi yakalama listesine geçirin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, anonim bir birleşim üyesi yakalar olduğundan C3492 oluşturur:  
  
```  
// C3492a.cpp  
  
int main()  
{  
   union  
   {  
      char ch;  
      int x;  
   };  
  
   ch = 'y';  
   [&x](char ch) { x = ch; }(ch); // C3492  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, UNION bir ad verip ve tam birleşim yapısı lambda ifadesi yakalama listesine geçirme C3492 çözer:  
  
```  
// C3492b.cpp  
  
int main()  
{  
   union  
   {  
      char ch;  
      int x;  
   } u;  
  
   u.ch = 'y';  
   [&u](char ch) { u.x = ch; }(u.ch);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)