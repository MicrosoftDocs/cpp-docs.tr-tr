---
title: "Derleyici Hatası C2015 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2015
dev_langs: C++
helpviewer_keywords: C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4669eec9d8134db6e024257855012eb78dcef95e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2015"></a>Derleyici Hatası C2015
çok fazla karakter sabiti  
  
 Karakter sabiti ikiden fazla karakter içeriyor. , Tek bir karakter için standart karakter sabitleri ve iki karakter uzunluğunda karakter sabitleri için sınırıdır.  
  
 \T gibi kaçış dizisi için tek bir karakter dönüştürülür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2015 oluşturur:  
  
```  
// C2015.cpp  
// compile with: /c  
  
char test1 = 'error';   // C2015  
char test2 = 'e';   // OK  
```  
  
## <a name="example"></a>Örnek  
 Ayrıca C2015 karakter sabitleri tamsayılara dönüştürülen bir Microsoft uzantısı kullanılarak ortaya çıkabilir.  Aşağıdaki örnek C2015 oluşturur:  
  
```  
// C2015b.cpp  
#include <stdio.h>  
  
int main()   
{  
    int a = 'abcde';   // C2015  
  
    int b = 'a';   // 'a' = ascii 0x61  
    printf_s("%x\n", b);  
}  
```