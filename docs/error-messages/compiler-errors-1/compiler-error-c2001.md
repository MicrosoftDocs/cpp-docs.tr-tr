---
title: Derleyici Hatası C2001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2001
dev_langs:
- C++
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f56eabbcb5ca322d7549c21a56893a8e13d9261
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2001"></a>Derleyici Hatası C2001
Yeni satır içinde sabiti  
  
 Aşağıdakileri sürece bir dize sabitine ikinci satırda devam edemiyor:  
  
-   İlk satır bir ters eğik çizgi ile bitmelidir.  
  
-   Çift tırnak işareti ile ilk satırdaki dize kapatın ve başka bir çift tırnak işaretiyle sonraki satıra dize açın.  
  
 İlk satırı \n ile biten yeterli değil.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2001 oluşturur:  
  
```  
// C2001.cpp  
// C2001 expected  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,  
             world");  
    printf_s("Hello,\n  
             world");  
}  
```  
  
## <a name="example"></a>Örnek  
 Satır devamlılığı karakteri sonra bir sonraki satıra başında boşluk dizesi sabitinde dahil edilir. Yukarıda gösterilen örnek hiçbiri yeni satır karakteri dize sabitine ekleyin. Aşağıda gösterildiği gibi yeni satır karakteri eklenebilir:  
  
```  
// C2001b.cpp  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,\n\  
             world");  
  
    printf_s("Hello,\  
             \nworld");  
  
    printf_s("Hello,\n"  
             "world");  
  
    printf_s("Hello,"  
             "\nworld");  
  
    printf_s("Hello,"  
             " world");  
  
    printf_s("Hello,\  
             world");  
}  
```