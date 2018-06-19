---
title: () Kod üretmez olmadan işlev adının kullanılması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40aed3969ae0707b07f0912d7247b49886d0319d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373988"
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