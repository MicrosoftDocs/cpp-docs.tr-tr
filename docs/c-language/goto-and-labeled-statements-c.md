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
ms.openlocfilehash: d84aa6701ef030dc494f6a40a7223d6f9bcd5073
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87199990"
---
# <a name="goto-and-labeled-statements-c"></a>goto ve Etiketli Deyimleri (C)

**`goto`** İfade denetimi bir etikete aktarır. Verilen etiket aynı işlevde bulunmalı ve aynı işlevde yalnızca bir deyimden önce görünebilirler.

## <a name="syntax"></a>Sözdizimi

*ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Etiketli ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sıçrama-deyim*

*sıçrama-deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`goto`**  *tanımlayıcı*  **;**

*etiketli ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*  **:**  *ifade*

Bir ifade etiketi yalnızca bir **`goto`** ifadeye anlam taşır; diğer bir bağlamda, etiketli bir ifade, etikete göre yürütülür.

Bir *sıçrama ifadesinin* aynı işlevde olması ve aynı işlevde yalnızca bir deyimden önce görünebilmesi gerekir. ' A ait *tanımlayıcı* adları kümesi **`goto`** kendi ad alanına sahiptir, bu nedenle adlar diğer tanımlayıcılarla karışmaz. Etiketler yeniden bildirilemez. Daha fazla bilgi için bkz. [ad alanları](../c-language/name-spaces.md) .

**`break`** **`continue`** Mümkün olduğunda,, ve **`return`** deyimlerinin tercih halinde kullanılması iyi bir programlama stilidir **`goto`** . **`break`** İfade yalnızca döngünün bir düzeyinden **`goto`** çıkıldığından, bir döngüyü derin iç içe döngülü çıkmak için gerekli olabilir.

Bu örnek, **`goto`** ifadesini gösterir:

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

Bu örnekte, bir ifade denetimi 0 ' a **`goto`** eşit olduğunda etiketli noktaya aktarır `stop` `i` .

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../c-language/statements-c.md)
