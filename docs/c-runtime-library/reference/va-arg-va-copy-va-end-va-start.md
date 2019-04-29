---
title: va_arg, va_copy, va_end, va_start
ms.date: 11/04/2016
apiname:
- va_arg
- va_end
- va_copy
- va_start
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- va_arg
- va_start
- va_list
- va_alist
- va_dcl
- va_copy
- va_end
helpviewer_keywords:
- variable argument lists, accessing
- va_start macro
- va_arg macro
- va_end macro
- arguments [C++], argument lists
- va_list macro
- va_dcl macro
- va_alist macro
- va_copy macro
ms.assetid: a700dbbd-bfe5-4077-87b6-3a07af74a907
ms.openlocfilehash: cc0a903f6bc4895f7d2ea6e80990dea94f28c6c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353579"
---
# <a name="vaarg-vacopy-vaend-vastart"></a>va_arg, va_copy, va_end, va_start

Değişken bağımsız değişken listeleri erişir.

## <a name="syntax"></a>Sözdizimi

```C
type va_arg(
   va_list arg_ptr,
   type
);
void va_copy(
   va_list dest,
   va_list src
); // (ISO C99 and later)
void va_end(
   va_list arg_ptr
);
void va_start(
   va_list arg_ptr,
   prev_param
); // (ANSI C89 and later)
void va_start(
   arg_ptr
);  // (deprecated Pre-ANSI C89 standardization version)
```

### <a name="parameters"></a>Parametreler

*type*<br/>
Alınması için bağımsız değişken türü.

*arg_ptr*<br/>
Bağımsız değişkenler listesine işaretçi.

*Hedef*<br/>
Gelen başlatılması için bağımsız değişkenler listesine işaretçi *src*

*src*<br/>
Başlatılmış kopyalamak için bağımsız değişkenler listesine işaretçi *dest*.

*prev_param*<br/>
Önündeki ilk isteğe bağlı bağımsız değişken parametresi.

## <a name="return-value"></a>Dönüş Değeri

**va_arg** geçerli bağımsız değişkenini döndürür. **va_copy**, **va_start** ve **va_end** değer döndürmüyor.

## <a name="remarks"></a>Açıklamalar

**Va_arg**, **va_copy**, **va_end**, ve **va_start** makrolar bağımsız değişken bir işleve erişmek için taşınabilir bir yol sağlar, işlev, değişken sayıda bağımsız değişken alır. Makroları iki sürümü vardır: STDARG içinde tanımlı makroları. H ISO C99 standart uygun; VARARG'LARDA tanımlı makroları. H kullanım dışı bırakılmıştır, ancak standart ANSI C89 önce yazılmış kod ile geriye dönük uyumluluk için korunur.

Bu makrolar, işlev gerekli bağımsız değişken isteğe bağlı bağımsız değişken bir sayı takip eder, sabit sayıda sürdüğünü varsayalım. Gerekli bağımsız değişkenler işleve sıradan parametre olarak bildirilir ve parametre adları erişilebilir. İsteğe bağlı bağımsız değişkenlere STDARG içindeki makrolar aracılığıyla erişilir. Y (veya VARARG'lara. H ANSI C89 standart önce yazılmış kod için), bağımsız değişken listesindeki ilk isteğe bağlı bağımsız değişkeni için bir işaretçi ayarlayan listeden bağımsız değişken alır ve bağımsız değişken işleme tamamlandığında işaretçisini sıfırlar.

STDARG içinde tanımlanan C Standart makroları. H, şu şekilde kullanılır:

- **va_start** ayarlar *arg_ptr* işleve geçirilen bağımsız değişken listesinde ilk isteğe bağlı bağımsız değişkeni. Bağımsız değişken *arg_ptr* olmalıdır **va_list** türü. Bağımsız değişken *prev_param* ilk isteğe bağlı bağımsız değişken bağımsız değişken listesinde hemen önce gelen gerekli parametre adı. Varsa *prev_param* bildirilmiş register depolama sınıfı ile makro davranışı tanımsızdır. **va_start** önce kullanılmalıdır **va_arg** ilk kez kullanılır.

- **va_arg** değerini alır. *türü* tarafından verilen konumda *arg_ptr*, artırır *arg_ptr* sonraki bağımsız değişken listesinde tarafından işaret etmek için boyutunu kullanarak *türü* sonraki bağımsız başladığı belirlemek için. **va_arg** olabilir herhangi sayıda bağımsız değişken listesinden almak için işlevde kullanılan.

- **va_copy** geçerli durumunda bir bağımsız değişken listesinde bir kopyasını getirir. *Src* parametresi zaten başlatılmalı ile **va_start**; bunu ile güncelleştirilmiş olabilir **va_arg** çağırır, ancak ile sıfırlandı gerekir değil **va_end** . Tarafından alınan sonraki bağımsız **va_arg** gelen *dest* hizmetinden alınan sonraki bağımsız olarak aynıdır *src*.

- Tüm bağımsız değişkenler aldıktan sonra **va_end** işaretçisi sıfırlar **NULL**. **va_end** ile başlatılan her bağımsız değişken listesi çağrılmalıdır **va_start** veya **va_copy** önce işlevi döndürür.

> [!NOTE]
> VARARGS makrolarındaki. H kullanım dışıdır ve olduğundan yalnızca geriye doğru uyumluluk için ANSI C89 standart önce yazılmış kod ile korunur. Diğer tüm durumlarda STDARGS makroları kullanın. H

Ne zaman bunlar kullanılarak derlenen [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md), bu makrolar kullanan programlar, yerel ve ortak dil çalışma zamanı (CLR) türü sistemleri farklılıklardan dolayı beklenmeyen sonuçlar oluşturabilir. Bu program göz önünde bulundurun:

```C
#include <stdio.h>
#include <stdarg.h>

void testit (int i, ...)
{
    va_list argptr;
    va_start(argptr, i);

    if (i == 0)
    {
        int n = va_arg(argptr, int);
        printf("%d\n", n);
    }
    else
    {
        char *s = va_arg(argptr, char*);
        printf("%s\n", s);
    }

    va_end(argptr);
}

int main()
{
    testit(0, 0xFFFFFFFF); // 1st problem: 0xffffffff is not an int
    testit(1, NULL);       // 2nd problem: NULL is not a char*
}
```

Dikkat **testit** bekliyor ya da, ikinci parametresinin bir **int** veya **char**<strong>\*</strong>. 0xffffffff geçirilen bağımsız değişkenler (bir **işaretsiz** **int**değil bir **int**) ve **NULL** (aslında bir **int**değil bir **char**<strong>\*</strong>). Program için yerel kod derlenir, bu çıktıyı oluşturur:

```Output
-1

(null)
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<stdio.h > ve \<stdarg.h >

**Kullanım dışı üstbilgisi:** \<XENIX >

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_va.c
// Compile with: cl /W3 /Tc crt_va.c
// The program below illustrates passing a variable
// number of arguments using the following macros:
//      va_start            va_arg              va_copy
//      va_end              va_list

#include <stdio.h>
#include <stdarg.h>
#include <math.h>

double deviation(int first, ...);

int main( void )
{
    /* Call with 3 integers (-1 is used as terminator). */
    printf("Deviation is: %f\n", deviation(2, 3, 4, -1 ));

    /* Call with 4 integers. */
    printf("Deviation is: %f\n", deviation(5, 7, 9, 11, -1));

    /* Call with just -1 terminator. */
    printf("Deviation is: %f\n", deviation(-1));
}

/* Returns the standard deviation of a variable list of integers. */
double deviation(int first, ...)
{
    int count = 0, i = first;
    double mean = 0.0, sum = 0.0;
    va_list marker;
    va_list copy;

    va_start(marker, first);     /* Initialize variable arguments. */
    va_copy(copy, marker);       /* Copy list for the second pass */
    while (i != -1)
    {
        sum += i;
        count++;
        i = va_arg(marker, int);
    }
    va_end(marker);              /* Reset variable argument list. */
    mean = sum ? (sum / count) : 0.0;

    i = first;                  /* reset to calculate deviation */
    sum = 0.0;
    while (i != -1)
    {
        sum += (i - mean)*(i - mean);
        i = va_arg(copy, int);
    }
    va_end(copy);               /* Reset copy of argument list. */
    return count ? sqrt(sum / count) : 0.0;
}
```

```Output
Deviation is: 0.816497
Deviation is: 2.236068
Deviation is: 0.000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişken Erişimi](../../c-runtime-library/argument-access.md)<br/>
[vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)<br/>
