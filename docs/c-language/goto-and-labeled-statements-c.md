---
title: goto ve Labeled Statements (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- labeled statement
- statements, labeled
- goto keyword [C]
ms.assetid: 3d0473dc-4b18-4fcc-9616-31a38499d7d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5183ff4f770ca0b6396835ed680b54fe13811e67
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080616"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Deyimler](../c-language/statements-c.md)