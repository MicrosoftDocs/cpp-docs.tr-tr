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
ms.openlocfilehash: b23e7e6310ba4ed968e2eac8e6d07d81ee4e79ba
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56151955"
---
# <a name="goto-and-labeled-statements-c"></a>goto ve Etiketli Deyimleri (C)

`goto` Deyime etiketine denetim aktarır. Belirtilen etiket, aynı işlevde bulunmalıdır ve aynı işlevde yalnızca bir deyim önce görünebilir.

## <a name="syntax"></a>Sözdizimi

*deyimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Etiketli deyim*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atlama-deyimi*

*atlama-deyimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**goto***tanımlayıcı***;**

*Etiketli deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı***:***deyimi*

Bir bildirim etiketi yalnızca anlamlı bir `goto` deyimi; diğer herhangi bir bağlam içinde etiketli deyim etiketi bakılmaksızın yürütülür.

A *atlama-deyimi* aynı işlevde bulunmalıdır ve aynı işlevde yalnızca bir deyim önce görünebilir. Dizi *tanımlayıcı* adları aşağıdaki bir `goto` kendi ad alanı adları ile diğer tanımlayıcılarla müdahale etmez bulunduğundan. Etiketleri bildirilemez. Bkz: [ad alanları](../c-language/name-spaces.md) daha fazla bilgi için.

İyi bir stili programlama **sonu**, **devam**, ve `return` preference için deyimi `goto` mümkün olduğunda. Bu yana **sonu** deyimi yalnızca bir döngü düzeyden çıkar bir `goto` iç içe döngü içinde bir döngüden çıkma için gerekli olabilir.

Bu örnek gösterir `goto` deyimi:

```
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

Bu örnekte, bir `goto` deyime aktarır denetim noktasına etiketli `stop` olduğunda `i` 5'e eşittir.

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../c-language/statements-c.md)
