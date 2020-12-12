---
description: 'Hakkında daha fazla bilgi edinin: va_arg, va_copy, va_end, va_start'
title: va_arg, va_copy, va_end, va_start
ms.date: 11/04/2016
api_name:
- va_arg
- va_end
- va_copy
- va_start
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 368a08e3ceb78d09d11a9f661772c6b0abef471f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299286"
---
# <a name="va_arg-va_copy-va_end-va_start"></a>va_arg, va_copy, va_end, va_start

Değişken bağımsız değişken listelerine erişir.

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

*türüyle*<br/>
Alınacak bağımsız değişkenin türü.

*arg_ptr*<br/>
Bağımsız değişken listesi işaretçisi.

*HD*<br/>
*Src* 'den başlatılacak bağımsız değişkenlerin listesi işaretçisi

*src*<br/>
*Hedefe* kopyalanacak bağımsız değişkenlerin başlatılmış listesinin işaretçisi.

*prev_param*<br/>
İlk isteğe bağlı bağımsız değişkenden önce gelen parametre.

## <a name="return-value"></a>Dönüş Değeri

**va_arg** geçerli bağımsız değişkeni döndürür. **va_copy**, **va_start** ve **va_end** değer döndürmez.

## <a name="remarks"></a>Açıklamalar

**Va_arg**, **va_copy**, **va_end** ve **va_start** makrolar, işlev değişken sayıda bağımsız değişken alırsa bir işleve bağımsız değişkenlere erişmek için taşınabilir bir yol sağlar. Makroların iki sürümü vardır: STDARG 'de tanımlanan makrolar. H ISO C99 standardına uygun; VARARGS içinde tanımlanan makrolar. H kullanım dışı bırakılmıştır, ancak ANSI c89 standardına göre yazılmış kodla geriye dönük uyumluluk için korunur.

Bu makrolar, işlevin sabit sayıda gerekli bağımsız değişken aldığını ve ardından değişken sayıda isteğe bağlı bağımsız değişken aldığını varsayar. Gerekli bağımsız değişkenler işleve normal parametreler olarak gösterilir ve parametre adlarıyla erişilebilir. İsteğe bağlı bağımsız değişkenlere STDARG içindeki makrolarla erişilir. H (veya VARARGS. H c89 Standard 'dan önce yazılan kod için), bağımsız değişken listesindeki ilk isteğe bağlı bağımsız değişkene bir işaretçi ayarlar, listedeki bağımsız değişkenleri alır ve bağımsız değişken işleme tamamlandığında işaretçiyi sıfırlar.

STDARG 'de tanımlanan C standart makroları. H, aşağıdaki gibi kullanılır:

- **va_start** , işleve geçirilen bağımsız değişkenler listesindeki ilk isteğe bağlı bağımsız değişkene *arg_ptr* ayarlar. *Arg_ptr* bağımsız değişkeni **va_list** türüne sahip olmalıdır. Bağımsız değişken *prev_param* bağımsız değişken listesindeki ilk isteğe bağlı bağımsız değişkenden hemen önce gelen gerekli parametrenin adıdır. *Prev_param* , YAZMAÇ depolama sınıfı ile bildirilirse, makronun davranışı tanımsızdır. **va_start** , **va_arg** ilk kez kullanılmadan önce kullanılmalıdır.

- **va_arg** , *arg_ptr* tarafından verilen konumdan *türünde* bir değer alır ve bir sonraki bağımsız değişkenin başladığı yeri anlamak için *tür* boyutunu kullanarak listedeki bir sonraki bağımsız değişkene işaret eden *arg_ptr* artırır. **va_arg** , işlev içindeki bağımsız değişkenleri almak için herhangi bir sayıda kez kullanılabilir.

- **va_copy** bir bağımsız değişken listesinin bir kopyasını geçerli durumunda yapar. *Src* parametresi zaten **va_start** ile başlatılmış olmalıdır; **va_arg** çağrılarıyla güncelleştirilmiş olabilir, ancak **va_end** sıfırlanmamalıdır. *Hedef* **va_arg** tarafından alınan sonraki bağımsız değişken *src*'den alınan sonraki bağımsız değişkenle aynıdır.

- Tüm bağımsız değişkenler alındıktan sonra, **va_end** işaretçiyi **null** olarak sıfırlar. **va_end** , işlevin dönüşmeden önce **va_start** veya **va_copy** ile başlatılan her bağımsız değişken listesinde çağrılmalıdır.

> [!NOTE]
> VARARGS içindeki makrolar. H kullanım dışıdır ve yalnızca ANSI c89 standardına göre yazılmış kodla geriye dönük uyumluluk için korunur. Diğer tüm durumlarda, STDARGS. H içindeki makroları kullanın.

[/Clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)kullanılarak derlendiklerinde, bu makroları kullanan programlar, yerel ve ortak dil çalışma zamanı (CLR) tür sistemleri arasındaki farklılıklar nedeniyle beklenmedik sonuçlar oluşturabilir. Bu programı göz önünde bulundurun:

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

**Tesıt** 'in ikinci parametresinin bir veya bir olduğunu beklediğini unutmayın **`int`** **`char*`** . Geçirilmekte olan bağımsız değişkenler 0xFFFFFFFF (bir **`unsigned int`** değil, değil **`int`** ) ve **null** (aslında **`int`** a değil **`char*`** ). Program yerel kod için derlendiğinde, bu çıktıyı oluşturur:

```Output
-1

(null)
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<stdio.h> ' \<stdarg.h>

**Kullanım dışı üst bilgi:**\<varargs.h>

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

[Bağımsız değişken erişimi](../../c-runtime-library/argument-access.md)<br/>
[vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)<br/>
