---
description: 'Hakkında daha fazla bilgi edinin: _scprintf, _scprintf_l, _scwprintf, _scwprintf_l'
title: _scprintf, _scprintf_l, _scwprintf, _scwprintf_l
ms.date: 3/9/2021
api_name:
- _scprintf_l
- _scwprintf
- _scwprintf_l
- _scprintf
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
- scprintf
- _scprintf_l
- _scwprintf_l
- _scprintf
- scwprintf
- _scwprintf
- scprintf_l
- _sctprintf_l
- scwprintf_l
- _sctprintf
helpviewer_keywords:
- scprintf function
- sctprintf_l function
- scwprintf_l function
- _scwprintf_l function
- _sctprintf_l function
- sctprintf function
- _scwprintf function
- _scprintf_l function
- _sctprintf function
- scprintf_l function
- formatted text [C++]
- _scprintf function
- scwprintf function
ms.openlocfilehash: 371b6053354e8b2bdc1b582c0088123a2d57c17d
ms.sourcegitcommit: b04b39940b0c1e265f80fc1951278fdb05a1b30a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102621730"
---
# <a name="_scprintf-_scprintf_l-_scwprintf-_scwprintf_l"></a>_scprintf, _scprintf_l, _scwprintf, _scwprintf_l

Biçimlendirilen dizedeki karakter sayısını döndürür.

## <a name="syntax"></a>Sözdizimi

```C
int _scprintf(
   const char *format [,
   argument] ...
);
int _scprintf_l(
   const char *format,
   locale_t locale [,
   argument] ...
);
int _scwprintf(
   const wchar_t *format [,
   argument] ...
);
int _scwprintf_l(
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
```

### <a name="parameters"></a>Parametreler

*formatını*<br/>
Biçim denetimi dizesi.

*değişkendir*<br/>
İsteğe bağlı bağımsız değişkenler.

*locale*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için bkz. [Biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

Dize yazdırılacaksa veya belirtilen biçimlendirme kodları kullanılarak bir dosyaya ya da arabelleğe gönderiliyorsa üretilecek karakter sayısını döndürür. Döndürülen değer, Sonlandırıcı null karakterini içermiyor. **_scwprintf** , geniş karakterler için aynı işlevi gerçekleştirir.

*Biçim* **null** Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1 döndürür ve **errno** , **EINVAL** olarak ayarlanır.

Bu ve diğer hata kodları hakkında bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Her *bağımsız değişken* (varsa), *biçimde* karşılık gelen biçim belirtimine göre dönüştürülür. Biçim sıradan karakterlerden oluşur ve [printf](printf-printf-l-wprintf-wprintf-l.md)için *Biçim* bağımsız değişkeniyle aynı form ve işleve sahiptir.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

> [!IMPORTANT]
> *Biçimin* Kullanıcı tanımlı bir dize olmadığından emin olun.
>
>
> Windows 10 sürüm 2004 (derleme 19041) ' den başlayarak, `printf` işlev ailesi, yuvarlama IÇIN ıeee 754 kurallarına göre tam olarak gösterilemeyen kayan nokta numaralarını yazdırır. Önceki Windows sürümlerinde, ' 5 ' ile biten tam olarak gösterilemeyen kayan noktalı sayılar her zaman yukarı yuvarlar. IEEE 754, en yakın çift basamağa ("Banker ' de yuvarlama" olarak da bilinir) yuvarlayabilmeleri gerektiğini belirtir. Örneğin, her ikisi `printf("%1.0f", 1.5)` de `printf("%1.0f", 2.5)` 2 ' ye yuvarlanmalıdır. 1,5, daha önce 2,5 2 ' ye yuvarlayacağından, 3 ' e yuvarlanacak. Bu değişiklik yalnızca tam olarak gösterilebilir tablo numaralarını etkiler. Örneğin, 2,35 (bellekte temsil edildiğinde, 2.35000000000000008 'e yaklaşmışsa), 2,4 ' e yuvarlamaya devam eder. Bu işlevler tarafından yapılan yuvarlama artık tarafından ayarlanan kayan nokta yuvarlama moduna da uyar [`fesetround`](fegetround-fesetround2.md) . Daha önce, yuvarlama her zaman açık `FE_TONEAREST` davranış. Bu değişiklik yalnızca Visual Studio 2019 sürüm 16,2 ve üzeri kullanılarak oluşturulan programları etkiler. Eski kayan nokta yuvarlama davranışını kullanmak için [' legacy_stdio_float_rounding. obj '](../link-options.md)ile bağlantı yapın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_sctprintf**|**_scprintf**|**_scprintf**|**_scwprintf**|
|**_sctprintf_l**|**_scprintf_l**|**_scprintf_l**|**_scwprintf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_scprintf**, **_scprintf_l**|\<stdio.h>|
|**_scwprintf**, **_scwprintf_l**|\<stdio.h> veya \<wchar.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt__scprintf.c

#define _USE_MATH_DEFINES

#include <stdio.h>
#include <math.h>
#include <malloc.h>

int main( void )
{
   int count;
   int size;
   char *s = NULL;

   count = _scprintf( "The value of Pi is calculated to be %f.\n",
                      M_PI);

   size = count + 1; // the string will need one more char for the null terminator
   s = malloc(sizeof(char) * size);
   sprintf_s(s, size, "The value of Pi is calculated to be %f.\n",
                      M_PI);
   printf("The length of the following string will be %i.\n", count);
   printf("%s", s);
   free( s );
}
```

```Output
The length of the following string will be 46.
The value of Pi is calculated to be 3.141593.
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vprintf Işlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
