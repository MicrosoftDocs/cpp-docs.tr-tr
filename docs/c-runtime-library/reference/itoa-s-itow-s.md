---
title: _itoa_s, _itow_s işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 03/21/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _itoa_s
- _ltoa_s
- _ultoa_s
- _i64toa_s
- _ui64toa_s
- _itow_s
- _ltow_s
- _ultow_s
- _i64tow_s
- _ui64tow_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _itoa_s
- _ltoa_s
- _ultoa_s
- _i64toa_s
- _ui64toa_s
- _itow_s
- _ltow_s
- _ultow_s
- _i64tow_s
- _ui64tow_s
- _itot_s
- _ltot_s
- _ultot_s
- _i64tot_s
- _ui64tot_s
- itoa_s
- ltoa_s
- ultoa_s
- i64toa_s
- ui64toa_s
- itow_s
- ltow_s
- ultow_s
- i64tow_s
- ui64tow_s
- itot_s
- ltot_s
- ultot_s
- i64tot_s
- ui64tot_s
dev_langs:
- C++
helpviewer_keywords:
- _ui64toa_s function
- _itow_s function
- _i64tow_s function
- _itot_s function
- converting integers
- itow_s function
- i64toa_s function
- _ui64tow_s function
- integers, converting
- _i64tot_s function
- itoa_s function
- _itoa_s function
- ui64toa_s function
- i64tow_s function
- converting numbers, to strings
- _ui64tot_s function
- _i64toa_s function
ms.assetid: eb746581-bff3-48b5-a973-bfc0a4478ecf
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f4d00b7938c9fce4e96cd900e460721d9ebe662
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="itoas-ltoas-ultoas-i64toas-ui64toas-itows--ltows--ultows-i64tows-ui64tows"></a>_itoa_s, _ltoa_s, _ultoa_s, _i64toa_s, _ui64toa_s, _itow_s, _ltow_s, _ultow_s, _i64tow_s, _ui64tow_s

Tamsayı bir dizeye dönüştürür. Sürümleri bunlar [_itoa, _itow işlevleri](itoa-itow.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _itoa_s( int value, char * buffer, size_t size, int radix );
errno_t _ltoa_s( long value, char * buffer, size_t size, int radix );
errno_t _ultoa_s( unsigned long value, char * buffer, size_t size, int radix );
errno_t _i64toa_s( long long value, char *buffer,
   size_t size, int radix );
errno_t _ui64toa_s( unsigned long long value, char *buffer,
   size_t size, int radix );

errno_t _itow_s( int value, wchar_t *buffer,
   size_t size, int radix );
errno_t _ltow_s( long value, wchar_t *buffer,
   size_t size, int radix );
errno_t _ultow_s( unsigned long value, wchar_t *buffer,
   size_t size, int radix );
errno_t _i64tow_s( long long value, wchar_t *buffer,
   size_t size, int radix );
errno_t _ui64tow_s( unsigned long long value, wchar_t *buffer,
   size_t size, int radix
);

// These template functions are C++ only:
template <size_t size>
errno_t _itoa_s( int value, char (&buffer)[size], int radix );

template <size_t size>
errno_t _ltoa_s( long value, char (&buffer)[size], int radix );

template <size_t size>
errno_t _ultoa_s( unsigned long value, char (&buffer)[size], int radix );

template <size_t size>
errno_t _itow_s( int value, wchar_t (&buffer)[size], int radix );

template <size_t size>
errno_t _ltow_s( long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
errno_t _ultow_s( unsigned long value, wchar_t (&buffer)[size], int radix );
```

### <a name="parameters"></a>Parametreler

*value*<br/>
Dönüştürülecek sayı.

*Arabellek*<br/>
Dönüştürme işleminin sonucu tutan çıkış arabelleği.

*Boyutu*<br/>
Boyutunu *arabellek* veya uluslararası karakter içinde.

*radix*<br/>
Sayı tabanını veya dönüştürmek için kullanılacak sayısal temel *değeri*, 2-36 aralığında olmalıdır.

## <a name="return-value"></a>Dönüş değeri

Başarılıysa sıfır; hatasında bir hata kodu. Aşağıdaki koşullardan biri geçerliyse, işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).

### <a name="error-conditions"></a>Hata koşulları

|value|Arabellek|size|sayı tabanını|Döndür|
|-----------|------------|----------------------|-----------|------------|
|tüm|**NULL**|tüm|tüm|**EINVAL**|
|tüm|tüm|<=0|tüm|**EINVAL**|
|tüm|tüm|< = gerekli sonucu dize uzunluğu|tüm|**EINVAL**|
|tüm|tüm|tüm|*sayı tabanını* < 2 veya *taban* > 36|**EINVAL**|

### <a name="security-issues"></a>Güvenlik sorunları

Bu işlevler, erişim ihlali oluşturabilir *arabellek* geçerli bellek göstermiyor ve değil **NULL**, veya arabellek uzunluğu Sonuç dizesini tutmak yeterince uzun değil.

## <a name="remarks"></a>Açıklamalar

Parametreler ve dönüş değeri dışında **_itoa_s** ve **_itow_s** işlevi aileleri sahip daha az güvenli ilgili olarak aynı davranışı **_itoa** ve **_itow** sürümleri.

C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

Bu işlevler hata ayıklama kitaplığı sürümleri ilk 0xFD arabellekle doldurun. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

CRT uzun olası değeri null Sonlandırıcı dahil olmak üzere her Tamsayı türünde dönüştürmek için gerekli olan arabellek boyutunu tanımlamak ve birkaç ortak temelleri için karakter imzalamak için uygun makroları içerir. Bilgi için bkz: [maksimum dönüştürme sayısı makroları](itoa-itow.md#maximum-conversion-count-macros).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_itot_s**|**_itoa_s**|**_itoa_s**|**_itow_s**|
|**_ltot_s**|**_ltoa_s**|**_ltoa_s**|**_ltow_s**|
|**_ultot_s**|**_ultoa_s**|**_ultoa_s**|**_ultow_s**|
|**_i64tot_s**|**_i64toa_s**|**_i64toa_s**|**_i64tow_s**|
|**_ui64tot_s**|**_ui64toa_s**|**_ui64toa_s**|**_ui64tow_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_itoa_s**, **_ltoa_s**, **_ultoa_s**, **_i64toa_s**, **_ui64toa_s**|\<stdlib.h >|
|**_itow_s**, **_ltow_s**, **_ultow_s**, **_i64tow_s**, **_ui64tow_s**|\<stdlib.h > veya \<wchar.h >|

Bu işlevler Microsoft özgüdür. Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu örnek tamsayı dönüştürme işlevleri bazılarını kullanımını göstermektedir. Unutmayın [_countof](countof-macro.md) makrosu dizi bildirimi derleyici ve işaretçiler decayed parametreler için görünür olduğunda arabellek boyutunu belirlemek için yalnızca çalışır.

```C
// crt_itoa_s.c
// Compile by using: cl /W4 crt_itoa_s.c
#include <stdlib.h>     // for _itoa_s functions, _countof, count macro
#include <stdio.h>      // for printf
#include <string.h>     // for strnlen

int main( void )
{
    char buffer[_MAX_U64TOSTR_BASE2_COUNT];
    int r;
    for ( r = 10; r >= 2; --r )
    {
        _itoa_s( -1, buffer, _countof(buffer), r );
        printf( "base %d: %s (%d chars)\n",
            r, buffer, strnlen(buffer, _countof(buffer)) );
    }
    printf( "\n" );
    for ( r = 10; r >= 2; --r )
    {
        _i64toa_s( -1LL, buffer, _countof(buffer), r );
        printf( "base %d: %s (%d chars)\n",
            r, buffer, strnlen(buffer, _countof(buffer)) );
    }
    printf( "\n" );
    for ( r = 10; r >= 2; --r )
    {
        _ui64toa_s( 0xffffffffffffffffULL, buffer, _countof(buffer), r );
        printf( "base %d: %s (%d chars)\n",
            r, buffer, strnlen(buffer, _countof(buffer)) );
    }
}
```

```Output
base 10: -1 (2 chars)
base 9: 12068657453 (11 chars)
base 8: 37777777777 (11 chars)
base 7: 211301422353 (12 chars)
base 6: 1550104015503 (13 chars)
base 5: 32244002423140 (14 chars)
base 4: 3333333333333333 (16 chars)
base 3: 102002022201221111210 (21 chars)
base 2: 11111111111111111111111111111111 (32 chars)

base 10: -1 (2 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)

base 10: 18446744073709551615 (20 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_itoa, _itow işlevleri](itoa-itow.md)<br/>
