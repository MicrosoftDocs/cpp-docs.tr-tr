---
description: 'Daha fazla bilgi edinin: goto deyimidir (C++)'
title: goto Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- goto_cpp
helpviewer_keywords:
- goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
ms.openlocfilehash: c8f94a5c2dfbd6ff3bd33223944180a4d1642b0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221390"
---
# <a name="goto-statement-c"></a>goto Deyimi (C++)

**`goto`** İfade, denetimi belirtilen tanımlayıcı tarafından etiketlenmiş ifadeye koşulsuz olarak aktarır.

## <a name="syntax"></a>Syntax

```
goto identifier;
```

## <a name="remarks"></a>Açıklamalar

Tarafından atanan etiketli deyimin `identifier` geçerli işlevde olması gerekir. Tüm `identifier` adlar dahili bir ad alanının üyeleridir ve bu nedenle diğer tanımlayıcılarla karışmaz.

Bir ifade etiketi yalnızca bir ifadeye anlam ifade edilir **`goto`** ; Aksi takdirde, ekstre etiketleri yok sayılır. Etiketler yeniden bildirilemez.

Bir **`goto`** deyimin, bu konumdaki kapsamda olan herhangi bir değişkenin başlatılmasına atlayan bir konuma denetim aktarmasına izin verilmez. Aşağıdaki örnek C2362 oluşturur:

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

**`break`** **`continue`** **`return`** Mümkün olduğunda deyim yerine,, ve deyimlerini kullanmak iyi bir programlama stilidir **`goto`** . Ancak, **`break`** ifade yalnızca bir döngü düzeyinden çıkış yaptığından, daha **`goto`** derin iç içe döngülü çıkmak için bir ifade kullanmanız gerekebilir.

Etiketler ve deyim hakkında daha fazla bilgi için **`goto`** bkz. [etiketli deyimler](../cpp/labeled-statements.md).

## <a name="example"></a>Örnek

Bu örnekte, bir **`goto`** ifade denetimi, 1 ' e eşit olduğunda etiketli noktaya aktarır `stop` `i` .

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
[Anahtar sözcükler](../cpp/keywords-cpp.md)
