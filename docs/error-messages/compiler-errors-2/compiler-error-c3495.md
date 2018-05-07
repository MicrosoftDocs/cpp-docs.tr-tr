---
title: Derleyici Hatası C3495 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3495
dev_langs:
- C++
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7accbc422256abbd75d518acce72c522fbb67c14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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


