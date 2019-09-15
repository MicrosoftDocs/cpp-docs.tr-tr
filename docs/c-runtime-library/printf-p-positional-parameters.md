---
title: printf_p Konumsal Parametreler
ms.date: 11/04/2016
api_location:
- msvcr120.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
helpviewer_keywords:
- _printf_p function, positional parameters
- printf_p function, positional parameters
ms.assetid: beb4fd85-a7aa-4665-9085-2c907a5b9ab0
ms.openlocfilehash: 156baa1a91931199ebca5f6200e239aa944fee1e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944056"
---
# <a name="printf_p-positional-parameters"></a>printf_p Konumsal Parametreler

Konumsal parametreler, bağımsız değişkenlerin bir biçim dizesindeki bir alana yerine geçen sayıya göre belirtme yeteneği sağlar. Aşağıdaki Konumsal parametre `printf` işlevleri kullanılabilir:

| Konumsal olmayan printf işlevleri | Konumsal parametre eşdeğerleri |
|---|---|
|[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|
|[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|[_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|
|[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|[_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l](../c-runtime-library/reference/cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)|
|[fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|
|[vprintf, _vprintf_l, vwprintf, _vwprintf_l](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[_vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)|
|[vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)|
|[vsprıntf, _vsprintf_l, vswprintf, _vswprintf_l, \__vswprintf_l](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|[_vsprintf_p, _vsprintf_p_l, _vswprintf_p, _vswprintf_p_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)|

## <a name="how-to-specify-positional-parameters"></a>Konumsal parametreleri belirtme

### <a name="parameter-indexing"></a>Parametre dizini oluşturma

Varsayılan olarak, konumsal biçimlendirme yoksa konumsal işlevler aynı şekilde konumsal olmayan şekilde davranır. Biçim belirticisinin başlangıcında kullanılacak konumsal parametresini `%n$` , burada `n` parametre listesinde biçimlendirilecek parametrenin konumudur olduğunu belirtirsiniz. Parametre konumu, biçim dizesinden sonraki ilk bağımsız değişken için 1 ' den başlar. Biçim belirticisinin geri kalanı `printf` biçim belirticisiyle aynı kurallara uyar. Biçim specörler hakkında daha fazla bilgi için bkz. [Biçim belirtimi sözdizimi: printf ve wprintf işlevleri](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

Konumsal biçimlendirme örneği aşağıda verilmiştir:

```C
_printf_p("%1$s %2$s", "November", "10");
```

Bu baskı:

```
November 10
```

Kullanılan sayıların sırasının bağımsız değişkenlerin sırasıyla eşleşmesi gerekmez. Örneğin, bu geçerli bir biçim dizesidir:

```C
_printf_p("%2$s %1$s", "November", "10");
```

Bu baskı:

```
10 November
```

Geleneksel biçim dizelerinin aksine, Konumsal parametreler biçim dizesinde birden çok kez kullanılabilir. Örneğin,

```C
_printf_p("%1$d times %1$d is %2$d", 10, 100);
```

Bu baskı:

```
10 times 10 is 100
```

Tüm bağımsız değişkenlerin, biçim dizesinde en az bir kez kullanıldığı bir yerde kullanılması gerekir. Bir biçim dizesinde izin verilen en fazla Konumsal parametre sayısı tarafından `_ARGMAX`verilir.

### <a name="width-and-precision"></a>Genişlik ve duyarlık

Bir Konumsal parametreyi `*n$` bir genişlik veya duyarlık belirticisi olarak belirtmek için kullanabilirsiniz; burada `n` , parametre listesinde Width veya Precision parametresinin konumudur. Width veya duyarlık değerinin konumu, \* simgenin hemen ardından gelmelidir. Örneğin,

```C
_printf_p("%1$*2$s","Hello", 10);
```

veya

```C
_printf_p("%2$*1$s", 10, "Hello");
```

### <a name="mixing-positional-and-non-positional-arguments"></a>Konumsal ve Konumsal olmayan bağımsız değişkenleri karıştırma

Konumsal parametreler, aynı biçim dizesinde konumsal olmayan parametrelerle karışmayabilir. Herhangi bir Konumsal biçimlendirme kullanılırsa, tüm biçim belirticileri konumsal biçimlendirme kullanmalıdır. Ancak, `printf_p` ve ilgili işlevler, Konumsal parametre içermeyen Biçim dizelerinde konumsal olmayan parametreleri desteklemeye devam eder.

## <a name="example"></a>Örnek

```C
// positional_args.c
// Build by using: cl /W4 positional_args.c
// Positional arguments allow the specification of the order
// in which arguments are consumed in a formatting string.

#include <stdio.h>

int main()
{
    int     i = 1,
            j = 2,
            k = 3;
    double  x = 0.1,
            y = 2.22,
            z = 333.3333;
    char    *s1 = "abc",
            *s2 = "def",
            *s3 = "ghi";

    // If positional arguments are unspecified,
    // normal input order is used.
    _printf_p("%d %d %d\n", i, j, k);

    // Positional arguments are numbers followed by a $ character.
    _printf_p("%3$d %1$d %2$d\n", i, j, k);

    // The same positional argument may be reused.
    _printf_p("%1$d %2$d %1$d\n", i, j);

    // The positional arguments may appear in any order.
    _printf_p("%1$s %2$s %3$s\n", s1, s2, s3);
    _printf_p("%3$s %1$s %2$s\n", s1, s2, s3);

    // Precision and width specifiers must be int types.
    _printf_p("%3$*5$f %2$.*4$f %1$*4$.*5$f\n", x, y, z, j, k);
}
```

```Output
1 2 3
3 1 2
1 2 1
abc def ghi
ghi abc def
333.333300 2.22 0.100
```

## <a name="see-also"></a>Ayrıca bkz.

[Biçim Belirtim Sözdizimi: printf ve wprintf İşlevleri](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)
