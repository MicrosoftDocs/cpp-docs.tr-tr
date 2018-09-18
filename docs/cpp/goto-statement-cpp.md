---
title: goto deyimi (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- goto_cpp
dev_langs:
- C++
helpviewer_keywords:
- goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c22a030ec0154f3a50d493e32e9bdeffdc05a2f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058269"
---
# <a name="goto-statement-c"></a>goto Deyimi (C++)

**Goto** deyimi koşulsuz olarak aktarır denetimi tarafından belirtilen tanımlayıcı etiketli deyim.

## <a name="syntax"></a>Sözdizimi

```
goto identifier;
```

## <a name="remarks"></a>Açıklamalar

Etiketli deyim tarafından belirlenen `identifier` geçerli işlev olmalıdır. Tüm `identifier` adları bir iç ad alanının üyeleri ve diğer tanımlayıcıları ile bu nedenle müdahale etmez.

Bir bildirim etiketi yalnızca anlamlı bir **goto** deyimi; Aksi takdirde, deyim etiketleri göz ardı edilir. Etiketleri bildirilemez.

A **goto** deyimi, denetimi kapsamında o konumda olan herhangi bir değişken başlatma üzerinden atlayan bir konuma aktarmanız izin verilmiyor. Aşağıdaki örnek C2362 başlatır:

```cpp
int goto_fn(bool b)
{
    if (!b)
    {
        goto exit;  // C2362
    }
    else
    { /*...*/ }

    int error_code = 42;

exit:
    return error_code;
}
```

İyi bir stili programlama **sonu**, **devam**, ve **dönüş** yerine deyimleri **goto** deyimi her olası. Ancak, çünkü **sonu** deyimi yalnızca bir döngü düzeyden çıkar, kullanmanız gerekebilir bir **goto** deyimi iç içe döngü çıkmak için.

Etiketler hakkında daha fazla bilgi ve **goto** deyimi bkz [etiketli deyimler](../cpp/labeled-statements.md).

## <a name="example"></a>Örnek

Bu örnekte, bir **goto** deyime aktarır denetim noktasına etiketli `stop` olduğunda `i` 3'e eşittir.

```cpp
// goto_statement.cpp
#include <stdio.h>
int main()
{
    int i, j;

    for ( i = 0; i < 10; i++ )
    {
        printf_s( "Outer loop executing. i = %d\n", i );
        for ( j = 0; j < 2; j++ )
        {
            printf_s( " Inner loop executing. j = %d\n", j );
            if ( i == 3 )
                goto stop;
        }
    }

    // This message does not print:
    printf_s( "Loop exited. i = %d\n", i );

    stop:
    printf_s( "Jumped to stop. i = %d\n", i );
}
```

```Output
Outer loop executing. i = 0
Inner loop executing. j = 0
Inner loop executing. j = 1
Outer loop executing. i = 1
Inner loop executing. j = 0
Inner loop executing. j = 1
Outer loop executing. i = 2
Inner loop executing. j = 0
Inner loop executing. j = 1
Outer loop executing. i = 3
Inner loop executing. j = 0
Jumped to stop. i = 3
```

## <a name="see-also"></a>Ayrıca bkz.

[Atlama Deyimleri](../cpp/jump-statements-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
