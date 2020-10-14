---
title: _Static_assert anahtar sözcüğü ve static_assert makrosu (C11)
description: C11 _Static_assert anahtar sözcüğünü ve C11 static_assert makrosunu açıklar.
ms.date: 10/13/2020
f1_keywords:
- static_assert_c
- _Static_assert
helpviewer_keywords:
- assertions [C], _Static_assert, static_assert
ms.openlocfilehash: dbe49b1dcbb8dd4e0d9df678f4456bc605e01c3f
ms.sourcegitcommit: 651348f8cd92ab0d52f09e9225a7eb41562559db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2020
ms.locfileid: "92061021"
---
# <a name="_static_assert-keyword-and-static_assert-macro-c11"></a>_Static_assert anahtar sözcüğü ve static_assert makrosu (C11)

Derleme zamanında bir onaylama testi sınar. Belirtilen sabit ifade ise **`false`** , derleyici belirtilen iletiyi görüntüler ve derleme C2338 hata vererek başarısız olur; aksi takdirde, hiçbir etkisi yoktur. C11 içinde yeni.

**`_Static_assert`** , C11 içinde tanıtılan bir anahtar sözcüktür.
**`static_assert`** , C11 ile tanıtılan ve anahtar sözcüğüne eşleyen bir makrodur **`_Static_assert`** .

## <a name="syntax"></a>Sözdizimi

```C
_Static_assert(constant-expression, string-literal);
static_assert(constant-expression, string-literal);
```

### <a name="parameters"></a>Parametreler

*Sabit ifadesi*\
Derleme zamanında değerlendirilebilen bir integral sabit ifadesi. İfade sıfırsa (false), *dize sabit değer* parametresini görüntüler ve derleme hata vererek başarısız olur. İfade sıfır değilse (true), hiçbir etkisi olmaz.

*dize sabit değeri*\
*Sabit ifade* sıfır (false) olarak değerlendirilirse görüntülenecek ileti. İleti, derleyicinin [temel karakter kümesi](../c-language/ascii-character-set.md) kullanılarak yapılmalıdır. Karakterler [çok baytlı veya geniş karakter](../c-language/multibyte-and-wide-characters.md)olamaz.

## <a name="remarks"></a>Açıklamalar

**`_Static_assert`** Anahtar sözcüğü ve makro, **`static_assert`** derleme zamanında yazılım onayını test et. Bunlar, genel veya işlev kapsamında kullanılabilirler.

Buna karşılık, [onaylama makrosu ve _assert ve _wassert işlevleri](../c-runtime-library/reference/assert-macro-assert-wassert.md) bir yazılım onayını çalışma zamanında test ediyor ve bir çalışma zamanı maliyetine neden olacak.

**Microsoft 'a özgü davranış**

C 'de, dahil olmadığınız durumlarda `<assert.h>` Microsoft Visual C/C++ derleyicisi, **`static_assert`** ile eşleşen bir anahtar sözcük olarak davranır **`_Static_assert`** . **`static_assert`** Aynı kod hem C hem de C++ ' da çalışacağından, kullanılması tercih edilir.

## <a name="example-of-a-compile-time-assert"></a>Derleme zamanı onayı örneği

Aşağıdaki örnekte **`static_assert`** ve **`_Static_assert`** numaralandırıcıların kaç öğe olduğunu doğrulamak için kullanılır ve bu tamsayılar 32 bit genişliğinde.

```C
// requires /std:c11 or higher
#include <assert.h>

enum Items
{
    A,
    B,
    C,
    LENGTH
};

int main()
{
    // _Static_assert is a C11 keyword
    _Static_assert(LENGTH == 3, "Expected Items enum to have three elements");

    // Preferred: static_assert maps to _Static_Assert and is compatible with C++
    static_assert(sizeof(int) == 4, "Expecting 32 bit integers"); 

    return 0;
}
```

## <a name="requirements"></a>Gereksinimler

|Makroya|Gerekli başlık|
|-------------|---------------------|
|**`static_assert`**|\<assert.h>|

## <a name="see-also"></a>Ayrıca bkz.

[_STATIC_ASSERT makro](../c-runtime-library/reference/static-assert-macro.md)\
[onaylama makrosu ve _assert ve _wassert işlevleri](../c-runtime-library/reference/assert-macro-assert-wassert.md) 
 [/std (dil standart sürümünü belirt)](../build/reference/std-specify-language-standard-version.md)