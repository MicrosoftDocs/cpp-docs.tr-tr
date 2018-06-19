---
title: Derleyici Hatası C3493 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3493
dev_langs:
- C++
helpviewer_keywords:
- C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3aec62bfff59396ec73141746193e4e3f16d84fa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257322"
---
# <a name="compiler-error-c3493"></a>Derleyici Hatası C3493
hiçbir varsayılan yakalama modu belirtilmediğinden 'var' örtük olarak yakalanamazsa  
  
 Boş lambda ifadesi yakalama `[]`, lambda ifadesi açıkça yapacağını belirtir veya örtülü hiçbir değişken yakalama.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Varsayılan bir yakalama modu sağlamak veya  
  
-   Açıkça bir veya daha fazla değişken yakalayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çünkü bir dış değişken değiştirir ancak boş yakalama yan tümcesi belirtir C3493 oluşturur:  
  
```  
// C3493a.cpp  
  
int main()  
{  
   int m = 55;  
   [](int n) { m = n; }(99); // C3493  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, başvuru tarafından varsayılan yakalama modu olarak belirterek C3493 çözümler.  
  
```  
// C3493b.cpp  
  
int main()  
{  
   int m = 55;  
   [&](int n) { m = n; }(99);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)