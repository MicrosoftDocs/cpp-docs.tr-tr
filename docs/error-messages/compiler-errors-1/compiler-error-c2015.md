---
title: Derleyici Hatası C2015 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2015
dev_langs:
- C++
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91c682aadeab5a572ec2bb5c2e649a1511af77ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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