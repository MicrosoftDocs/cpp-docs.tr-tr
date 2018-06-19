---
title: _CrtSetDebugFillThreshold | Microsoft Docs
ms.custom: ''
ms.date: 03/21/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetDebugFillThreshold
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
- _CrtSetDebugFillThreshold
- CrtSetDebugFillThreshold
dev_langs:
- C++
helpviewer_keywords:
- debug, buffer-filling behavior
- CrtSetDebugFillThreshold function
- _CrtSetDebugFillThreshold function
- buffer-filling behavior
- 0xFD
ms.assetid: 6cb360e8-56ae-4248-b17f-e28aee3e0ed7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0980331389a36fa123c6ee64989296f5afec5c8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398665"
---
# <a name="crtsetdebugfillthreshold"></a>_CrtSetDebugFillThreshold

Alır ya da hata ayıklama işlevlerinde arabellek doldurma davranışı denetleme eşik değiştirir.

## <a name="syntax"></a>Sözdizimi

```C
size_t _CrtSetDebugFillThreshold( size_t newThreshold );
```

### <a name="parameters"></a>Parametreler

*newThreshold*<br/>
Yeni eşik boyutunu bayt cinsinden.

## <a name="return-value"></a>Dönüş değeri

Önceki eşik değeri.

## <a name="remarks"></a>Açıklamalar

Bazı gelişmiş güvenlik CRT işlevleri hata ayıklama sürümleri ile özel bir karakter onlara geçirilen arabellek doldurma (0xFE). Bu durumlarda boyutu yanlış işlev için burada geçildi bulmak için yardımcı olur. Ne yazık ki, performans de azaltır. Performansı artırmak için kullanıyoruz **_CrtSetDebugFillThreshold** arabellek doldurma büyük arabellekleri için devre dışı bırakmak için *newThreshold* eşiği. A *newThreshold* 0 değerini devre dışı bırakır, tüm arabellekleri için.

Varsayılan Eşik **SIZE_T_MAX**.

Burada, etkilenen işlevlerin bir listesi verilmiştir.

- [_ecvt_s](ecvt-s.md)

- [_fcvt_s](fcvt-s.md)

- [_gcvt_s](gcvt-s.md)

- [_itoa_s, _ltoa_s, _ultoa_s, _i64toa_s, _ui64toa_s, _itow_s, _ltow_s, _ultow_s, _i64tow_s, _ui64tow_s](itoa-s-itow-s.md)

- [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)

- [_mbsnbcat_s, _mbsnbcat_s_l](mbsnbcat-s-mbsnbcat-s-l.md)

- [_mbsnbcpy_s, _mbsnbcpy_s_l](mbsnbcpy-s-mbsnbcpy-s-l.md)

- [_mbsnbset_s, _mbsnbset_s_l](mbsnbset-s-mbsnbset-s-l.md)

- [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)

- [strcat_s, wcscat_s, _mbscat_s](strcat-s-wcscat-s-mbscat-s.md)

- [strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)

- [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md)

- [_strlwr_s, _strlwr_s_l, _mbslwr_s, _mbslwr_s_l, _wcslwr_s, _wcslwr_s_l](strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)

- [strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)

- [strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)

- [_strnset_s, _strnset_s_l, _wcsnset_s, _wcsnset_s_l, _mbsnset_s, _mbsnset_s_l](strnset-s-strnset-s-l-wcsnset-s-wcsnset-s-l-mbsnset-s-mbsnset-s-l.md)

- [_strset_s, _strset_s_l, _wcsset_s, _wcsset_s_l, _mbsset_s, _mbsset_s_l](strset-s-strset-s-l-wcsset-s-wcsset-s-l-mbsset-s-mbsset-s-l.md)

- [_strupr_s, _strupr_s_l, _mbsupr_s, _mbsupr_s_l, _wcsupr_s, _wcsupr_s_l](strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtSetDebugFillThreshold**|\<crtdbg.h >|

Microsoft'a özgü işlevdir. Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

```C
// crt_crtsetdebugfillthreshold.c
// compile with: cl /MTd crt_crtsetdebugfillthreshold.c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <crtdbg.h>

void Clear( char buff[], size_t size )
{
   for( int i=0; i<size; ++i )
      buff[i] = 0;
}

void Print( char buff[], size_t size )
{
   for( int i=0; i<size; ++i )
      printf( "%02x  %c\n", (unsigned char)buff[i], buff[i] );
}

int main( void )
{
   char buff[10];

   printf( "With buffer-filling on:\n" );
   strcpy_s( buff, _countof(buff), "howdy" );
   Print( buff, _countof(buff) );

   _CrtSetDebugFillThreshold( 0 );

   printf( "With buffer-filling off:\n" );
   Clear( buff, _countof(buff) );
   strcpy_s( buff, _countof(buff), "howdy" );
   Print( buff, _countof(buff) );
}
```

```Output
With buffer-filling on:
68  h
6f  o
77  w
64  d
79  y
00
fe  ■
fe  ■
fe  ■
fe  ■
With buffer-filling off:
68  h
6f  o
77  w
64  d
79  y
00
00
00
00
00
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
