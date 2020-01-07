---
title: goto ve Etiketli Deyimleri (C)
ms.date: 11/04/2016
f1_keywords:
- goto
helpviewer_keywords:
- labeled statement
- statements, labeled
- goto keyword [C]
ms.assetid: 3d0473dc-4b18-4fcc-9616-31a38499d7d7
ms.openlocfilehash: b5e0d602332c87510b1fe5f59db3e497b88f0acb
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75299123"
---
# <a name="goto-and-labeled-statements-c"></a>goto ve Etiketli Deyimleri (C)

`goto` ifade denetimi bir etikete aktarır. Verilen etiket aynı işlevde bulunmalı ve aynı işlevde yalnızca bir deyimden önce görünebilirler.

## <a name="syntax"></a>Sözdizimi

*ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*etiketli ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sıçrama-deyim*

*sıçrama-deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**goto** *tanımlayıcı* **;**

*etiketli ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı* **:** *deyimi*

Bir ifade etiketi yalnızca bir `goto` bildirimine göre anlamlıdır; diğer bir bağlamda, etiketli bir ifade, etikete göre yürütülür.

Bir *sıçrama ifadesinin* aynı işlevde olması ve aynı işlevde yalnızca bir deyimden önce görünebilmesi gerekir. `goto` izleyen *tanımlayıcı* adları kümesi kendi ad alanına sahiptir, bu nedenle adlar diğer tanımlayıcılarla karışmaz. Etiketler yeniden bildirilemez. Daha fazla bilgi için bkz. [ad alanları](../c-language/name-spaces.md) .

Mümkün olan her durumda `goto` için **kesme**, **devam**ve `return` deyimin tercih halinde kullanılması iyi bir programlama stilidir. **Break** deyimleri yalnızca döngünün bir düzeyinden çıkdığından, bir döngüyü derin iç içe döngülü çıkmak için bir `goto` gerekebilir.

Bu örnek `goto` ifadesini gösterir:

```c
// goto.c
#include <stdio.h>

int main()
{
    int i, j;

    for ( i = 0; i < 10; i++ )
    {
        printf_s( "Outer loop executing. i = %d\n", i );
        for ( j = 0; j < 3; j++ )
        {
            printf_s( " Inner loop executing. j = %d\n", j );
            if ( i == 5 )
                goto stop;
        }
    }

    /* This message does not print: */
    printf_s( "Loop exited. i = %d\n", i );

    stop: printf_s( "Jumped to stop. i = %d\n", i );
}
```

Bu örnekte, `goto` bir ifade denetimi, `i`, 5 ' e eşit `stop` etiketli noktaya aktarır.

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../c-language/statements-c.md)
