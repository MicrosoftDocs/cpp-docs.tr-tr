---
title: Derleyici Hatası C3496 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3496
dev_langs:
- C++
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dbc128c1e9a80c61ad42514827bbf8d47b693e84
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33256993"
---
# <a name="compiler-error-c3496"></a>Derleyici Hatası C3496
'this' değeri her zaman yakalanır: '&' yoksayıldı  
  
 Yakalama yapılamaz `this` başvuruya işaretçi.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Yakalama `this` değeriyle işaretçi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3496 oluşturur çünkü bir başvuru `this` işaretçi lambda ifadesi yakalama listede görünür:  
  
```  
// C3496.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      [&this] {}(); // C3496  
   }  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)