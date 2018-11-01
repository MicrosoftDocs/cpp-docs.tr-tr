---
title: printf_p Konumsal Parametreler
ms.date: 11/04/2016
apilocation:
- msvcr120.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
apitype: DLLExport
helpviewer_keywords:
- _printf_p function, positional parameters
- printf_p function, positional parameters
ms.assetid: beb4fd85-a7aa-4665-9085-2c907a5b9ab0
ms.openlocfilehash: 2801f1b4c61247ebb9a1402b6244f0c63c2b7dd2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498039"
---
# <a name="printfp-positional-parameters"></a>printf_p Konumsal Parametreler

Konumsal parametreleri olan bağımsız değişkenlerin biçim dizesindeki bir alana atanması numarasına göre belirtme olanağı sağlar. Aşağıdaki konumsal parametresini `printf` işlevleri kullanılabilir:

| Konumsal olmayan printf işlevleri | Konumsal parametresi eşdeğerleri |
|---|---|
|[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|
|[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|[_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|
|[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|[_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l](../c-runtime-library/reference/cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)|
|[fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|
|[vprintf, _vprintf_l, vwprintf, _vwprintf_l](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[_vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)|
|[vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)|
|[vsprintf, _vsprintf_l, vswprintf, _vswprintf_l, \__vswprintf_l](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|[_vsprintf_p, _vsprintf_p_l, _vswprintf_p, _vswprintf_p_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)|

## <a name="how-to-specify-positional-parameters"></a>Konumsal parametreler belirtme

### <a name="parameter-indexing"></a>Parametre dizini oluşturma

Konumsal bir biçimlendirmesi olmayan mevcut değilse varsayılan olarak, konumsal işlevleri konumsal olmayan ayarlara aynı şekilde davranır. Konumsal parametresini kullanarak belirttiğiniz `%n$` biçim belirticisi başında nerede `n` parametre listesinde biçimlendirmek için parametre konumudur. Parametre konumu 1 ilk bağımsız değişken için Biçim dizesinden sonra başlar. Biçim belirticisinin kalan olarak aynı kurallara `printf` biçim belirticisi. Biçim specfiers hakkında daha fazla bilgi için bkz: [biçim belirtim Sözdizimi: printf ve wprintf işlevleri](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

Konumsal biçimlendirme bir örnek aşağıda verilmiştir:

```C
_printf_p("%1$s %2$s", "November", "10");
```

Bu yazdırır:

```
November 10
```

Kullanılan numaralarının sırasını bağımsız değişkenlerin sırası eşleşmesi gerekmez. Örneğin, bu geçerli bir biçim dizesi.

```C
_printf_p("%2$s %1$s", "November", "10");
```

Bu yazdırır:

```
10 November
```

Geleneksel Biçim dizeleri, konumsal parametreler bir biçim dizesinde birden çok kez kullanılabilir. Örneğin,

```C
_printf_p("%1$d times %1$d is %2$d", 10, 100);
```

Bu yazdırır:

```
10 times 10 is 100
```

Tüm bağımsız değişkenlerin biçim dizesindeki en az bir kez bir yere kullanılmalıdır. Konumsal parametreler bir biçim dizesi için izin verilen en fazla sayısını tarafından verilen `_ARGMAX`.

### <a name="width-and-precision"></a>Genişlik ve duyarlık

Kullanabileceğiniz `*n$` konumsal bir parametre bir genişlik veya duyarlık belirtici olarak belirtmek için burada `n` genişliğini veya duyarlık parametresi parametre listesindeki konumudur. Genişlik veya duyarlık değeri konumunu hemen arkasından görünmelidir \* simgesi. Örneğin,

```C
_printf_p("%1$*2$s","Hello", 10);
```

veya

```C
_printf_p("%2$*1$s", 10, "Hello");
```

### <a name="mixing-positional-and-non-positional-arguments"></a>Konumsal ve konumsal olmayan bağımsız değişkenler karıştırma

Konumsal parametreler aynı Biçim dizesinde konumsal olmayan parametrelerle karışabilir. Konumsal bir biçimlendirme kullanılırsa, biçim belirticileri tüm konumsal biçimlendirme kullanmanız gerekir. Ancak, `printf_p` ve ilgili işlevler yine de konumsal olmayan parametreler hiçbir konumsal parametreler içeren biçim dizeleri destekler.

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

## <a name="see-also"></a>Ayrıca Bkz.

[Biçim Belirtim Sözdizimi: printf ve wprintf İşlevleri](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)