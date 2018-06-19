---
title: Derleyici Hatası C3492 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3492
dev_langs:
- C++
helpviewer_keywords:
- C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de9fb29b13c1bbae7c86f80da53c11590e7c7d2b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253580"
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