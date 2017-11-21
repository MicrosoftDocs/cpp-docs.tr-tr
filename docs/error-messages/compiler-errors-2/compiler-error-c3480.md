---
title: "Derleyici Hatası C3480 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3480
dev_langs: C++
helpviewer_keywords: C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d84314d20ea00e880981e418c2b5b11008f74229
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3480"></a>Derleyici Hatası C3480
'var': kapsayan bir işlev kapsamdan bir lambda yakalama değişken olmalıdır  
  
 Lambda yakalama değişkeni kapsayan bir işlev kapsamından değil.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Değişkeni lambda ifadesi yakalama listesinden kaldırın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3480 oluşturur çünkü değişkeni `global` kapsayan bir işlev kapsamından değil:  
  
```  
// C3480a.cpp  
  
int global = 0;  
int main()  
{  
   [&global] { global = 5; }(); // C3480  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek değişkeni kaldırarak C3480 çözümler `global` lambda ifadesi yakalama listesinden:  
  
```  
// C3480b.cpp  
  
int global = 0;  
int main()  
{  
   [] { global = 5; }();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md)