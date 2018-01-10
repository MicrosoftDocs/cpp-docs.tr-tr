---
title: "Derleyici Hatası C2148 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2148
dev_langs: C++
helpviewer_keywords: C2148
ms.assetid: e510c2c9-7b57-4ce8-be03-ba363e2cc5d9
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 66789b0ae6b162f33000299974edf488e2c44aa6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2148"></a>Derleyici Hatası C2148
dizi toplam boyutu 0x7fffffff baytı aşmamalıdır  
  
 Bir dizi sınırını aşıyor. Dizinin boyutunu azaltın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2148 oluşturur:  
  
```  
// C2148.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( ) {  
   char MyArray[0x7ffffffff];   // C2148  
   char * MyArray2 = (char *)malloc(0x7fffffff);  
  
   if (MyArray2)  
      printf_s("It worked!");  
   else  
      printf_s("It didn't work.");  
}  
```