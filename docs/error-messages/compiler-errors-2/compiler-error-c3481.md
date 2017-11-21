---
title: "Derleyici Hatası C3481 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3481
dev_langs: C++
helpviewer_keywords: C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 33bd3d85a4cf44741d59ccb81259babd34704b69
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3481"></a>Derleyici Hatası C3481
'var': lambda yakalama değişkeni bulunamadı  
  
 Derleyici lambda ifadesi yakalama listesine geçirilen bir değişken tanımı bulunamadı.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Değişkeni lambda ifadesi yakalama listesinden kaldırın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3481 oluşturur çünkü değişkeni `n` tanımlı değil:  
  
```  
// C3481.cpp  
  
int main()  
{  
   [n] {}(); // C3481  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md)