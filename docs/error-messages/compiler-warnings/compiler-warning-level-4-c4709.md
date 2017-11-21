---
title: "Derleyici Uyarısı (düzey 4) C4709 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4709
dev_langs: C++
helpviewer_keywords: C4709
ms.assetid: 8abfdd45-8c70-4c27-b0fb-ca0c3f0fccf9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d7e3fb78715063813215eaa505850d8bbbe4cf7f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4709"></a>Derleyici Uyarısı (düzey 4) C4709
dizi dizini ifadesi içinde virgül işleci  
  
 Bir dizi dizini ifadede virgül ortaya çıktığında derleyici sonra son virgül değeri kullanır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4709 oluşturur:  
  
```  
// C4709.cpp  
// compile with: /W4  
#include <stdio.h>  
  
int main()   
{  
    int arr[2][2];  
    arr[0][0] = 10;  
    arr[0][1] = 11;  
  
    // Prints 10, not 11  
    printf_s("\n%d",arr[0][1,0]);   // C4709  
}  
```