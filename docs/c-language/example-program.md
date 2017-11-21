---
title: "Örnek Program | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: fc22ef82-9caa-425f-b201-2891bc123d1f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 976b3c21e24a8e1e6c99664b31d32f85985d7f55
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="example-program"></a>Örnek Program
Aşağıdaki C kaynak program iki kaynak dosyaları içerir. Bazı çeşitli bildirimler ve tanımlar C programı'olası bir bakış sağlar. Bu kitap sonraki bölümlerde bu bildirimler, tanımları ve başlatmaları yazma ve C anahtar sözcükleri gibi kullanmayı açıklar **statik** ve `extern`. `printf` İşlevi C üstbilgi dosyasında STDIO bildirildi. H.  
  
 `main` Ve `max` işlevleri varsayılır ayrı dosyalarda ve programın yürütülmesi başlıyorsa `main` işlevi. Hiçbir açık kullanıcı işlevleri önce yürütülür `main`.  
  
```  
/*****************************************************************  
                    FILE1.C - main function  
*****************************************************************/  
  
#define ONE     1  
#define TWO     2  
#define THREE   3  
#include <stdio.h>  
  
int a = 1;                       // Defining declarations      
int b = 2;                       //  of external variables      
  
extern int max( int a, int b );  // Function prototype          
  
int main()                       // Function definition         
{                                //  for main function          
    int c;                       // Definitions for      
    int d;                       //  two uninitialized  
                                 //  local variables  
  
    extern int u;                // Referencing declaration     
                                 //  of external variable       
                                 //  defined elsewhere          
    static int v;                // Definition of variable      
                                 //  with continuous lifetime   
  
    int w = ONE, x = TWO, y = THREE;  
    int z = 0;  
  
    z = max( x, y );             // Executable statements      
    w = max( z, w );  
    printf_s( "%d %d\n", z, w );  
    return 0;  
}  
  
/****************************************************************  
            FILE2.C - definition of max function  
****************************************************************/  
  
int max( int a, int b )          // Note formal parameters are     
                                 //  included in function header   
{  
    if( a > b )  
        return( a );  
    else  
        return( b );  
}  
```  
  
 DOSYA1. C içeren prototipi `max` işlevi. İşlevi kullanılmadan önce bildirildiğinden bu tür bir bildirimi bazen "ileriye dönük bildirimi" adı verilir. Tanımı `main` işlev çağrıları içeren `max`.  
  
 İle başlayan satırlar `#define` önişlemci yönergeleri. Önişlemci tanımlayıcıları değiştirmek için bu yönergeleri söyleyin `ONE`, `TWO`, ve `THREE` numaralarıyla `1`, `2`, ve `3`, sırasıyla dosya1 boyunca. C Ancak, yönergeleri dosya2 için geçerli değildir. Ayrı olarak derlenmiş ve dosya1 ile bağlantılı C. C Satır başlayarak `#include` STDIO dosya eklemek için derleyici söyler. İçin prototip içeren H `printf` işlevi. [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md) açıklanacak *önişlemci başvurusu*.  
  
 DOSYA1. Genel değişkenler başlatmak için bildirimler tanımlama C kullanır `a` ve `b`. Yerel değişkenler `c` ve `d` bildirilmiş ancak başlatılmamış. Depolama için tüm bu değişkenleri tahsis edilir. Statik ve dış değişkenleri `u` ve `v`, 0'a otomatik olarak başlatılır. Bu nedenle yalnızca `a`, `b`, `u`, ve `v` bunlar, açıkça veya örtük başlatıldığından bildirirken anlamlı değerleri içerir. DOSYA2. C işlev tanımını içeren `max`. Çağrıları bu tanımı karşılayan `max` dosya1 içinde. C  
  
 Ömür ve görünürlük tanımlayıcıların ele alınmıştır [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md). İşlevler hakkında daha fazla bilgi için bkz: [işlevler](../c-language/functions-c.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak dosyalar ve kaynak programlar](../c-language/source-files-and-source-programs.md)