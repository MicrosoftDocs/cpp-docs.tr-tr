---
title: () Kod üretmez olmadan işlev adının kullanılması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c03706be0b9853cbbdebe79b58e410f7237692ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-function-name-without--produces-no-code"></a>() Olmadan İşlev Adının Kullanılması Kod Üretmez
Programınıza bildirilen bir işlev adı parantez olmadan kullanıldığında, derleyici kod üretmez. Bu işlev adresi derleyici hesaplar çünkü olsun veya olmasın işlev parametreleri alır bağımsız olarak gerçekleşir; İşlev çağırma işleci (")" mevcut olmadığından, ancak hiçbir çağrı yapılır. Bu sonuç aşağıdakine benzer:  
  
```  
// compile with /Wall to generate a warning  
int a;  
a;      // no code generated here either  
```  
  
 Visual C++'da, hatta uyarı düzeyini 4 kullanarak tanılama çıktı oluşturur. Hiçbir uyarı görüntülenir; kod oluşturulur.  
  
 Aşağıdaki örnek kod (bir uyarıyla) derler ve bağlantıları doğru hatasız ancak reference için kod üretmez `funcn( )`. Bu doğru çalışması işlev çağırma işleci (")" ekleyin.  
  
```  
#include <stdio.h>  
void funcn();  
  
int main() {  
   funcn;      /* missing function call operator;   
                  call will fail.  Use funcn() */  
   }  
  
void funcn() {  
   printf("\nHello World\n");  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kodunuzu İyileştirme](../../build/reference/optimizing-your-code.md)