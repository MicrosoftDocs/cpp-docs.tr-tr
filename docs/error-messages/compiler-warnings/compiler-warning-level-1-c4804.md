---
title: "Derleyici Uyarısı (düzey 1) C4804 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4804
dev_langs: C++
helpviewer_keywords: C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 95a96844406bb803c46bd4f1b0162be711105394
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4804"></a>Derleyici Uyarısı (düzey 1) C4804
'işlemi': işlem ' bool' türünün güvensiz kullanımı  
  
 Bu uyarı için kullanıldığında bir `bool` değişken veya beklenmeyen bir şekilde değer. Negatif birli işleç gibi işleçlerin kullanırsanız, örneğin, C4804 oluşturulur (**-**) veya tamamlama işleci (`~`). Derleyici ifadeyi hesaplar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4804 oluşturur:  
  
```  
// C4804.cpp  
// compile with: /W1  
  
int main()  
{  
   bool i = true;  
   if (-i)   // C4804, remove the '-' to resolve  
   {  
      i = false;  
   }  
}  
```