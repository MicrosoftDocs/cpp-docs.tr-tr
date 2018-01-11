---
title: "Derleyici Hatası C3495 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3495
dev_langs: C++
helpviewer_keywords: C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3818f42410fd97d5df9b157828658c30ac9974e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3495"></a>Derleyici Hatası C3495
'var': lambda yakalama otomatik depolama süresi olması gerekir  
  
 İşaretlenmiş bir değişkeni gibi otomatik depolama süresi sahip olmayan bir değişken yakalayamazsınız `static` veya `extern`.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Değil geçirmek bir `static` veya `extern` lambda ifadesi yakalama listesine değişken.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3495 oluşturur çünkü `static` değişkeni `n` lambda ifadesi yakalama listesi görüntülenir:  
  
```  
// C3495.cpp  
  
int main()  
{  
   static int n = 66;  
   [&n]() { return n; }(); // C3495  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)   


