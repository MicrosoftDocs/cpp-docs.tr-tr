---
title: strspn, wcsspn, _mbsspn, _mbsspn_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbsspn_l
- wcsspn
- strspn
- _mbsspn
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ftcsspn
- wcsspn
- _mbsspn
- _tcsspn
- strspn
dev_langs:
- C++
helpviewer_keywords:
- wcsspn function
- strings [C++], searching
- mbsspn function
- tcsspn function
- strspn function
- substrings, finding
- _mbsspn_l function
- ftcsspn function
- _mbsspn function
- _ftcsspn function
- mbsspn_l function
- _tcsspn function
ms.assetid: d077284a-809f-4068-959e-c6d6262677eb
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 616c00f1e5043788591d47fabfcbadab44dba654
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="strspn-wcsspn-mbsspn-mbsspnl"></a>strspn, wcsspn, _mbsspn, _mbsspn_l

İlk karakter dizinini karakter kümesine ait olmayan bir dize döndürür.

> [!IMPORTANT]
> **_mbsspn** ve **_mbsspn_l** Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
size_t strspn(
   const char *str,
   const char *strCharSet
);
size_t wcsspn(
   const wchar_t *str,
   const wchar_t *strCharSet
);
size_t _mbsspn(
   const unsigned char *str,
   const unsigned char *strCharSet
);
size_t _mbsspn_l(
   const unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Aranacak dize null ile sonlandırılmış.

*strCharSet*<br/>
Null olarak sonlandırılan bir karakter kümesi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Substring uzunluğu belirten bir tamsayı değeri döndürür *str* , oluşur tamamen karakter *strCharSet*. Varsa *str* içinde değil karakteriyle başlayan *strCharSet*, işlevi 0 değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**Strspn** işlevi adındaki ilk karakter dizinini döndürür *str* ait olmayan karakter kümesine *strCharSet*. Arama null karakterlerini sonlandırma içermez.

**wcsspn** ve **_mbsspn** joker karakter ve çok baytlı karakter sürümleri **strspn**. Bağımsız değişkenleri **wcsspn** joker karakter olan dizeleri; bu **_mbsspn** çok baytlı karakter dizeleri belirtilmiştir. **_mbsspn** parametrelerini doğrular. Varsa *str* veya *strCharSet* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa **_mbspn** ayarlar **errno** için **EINVAL** ve 0 döndürür. **strspn** ve **wcsspn** parametrelerini doğrulamaz. Bu üç işlevler aynı şekilde aksi davranır.

Çıkış değerini ayarı tarafından etkilenen **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; sürümleriyle **_l** soneki, yerel ayar parametresi kullanmasını dışında aynıdır Bunun yerine geçirildi. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsspn**|**strspn**|**_mbsspn**|**wcsspn**|
|**yok**|**yok**|**_mbsspn_l**|**yok**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strspn**|\<String.h >|
|**wcsspn**|\<String.h > veya \<wchar.h >|
|**_mbsspn**, **_mbsspn_l**|\<Mbstring.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strspn.c
// This program uses strspn to determine
// the length of the segment in the string "cabbage"
// consisting of a's, b's, and c's. In other words,
// it finds the first non-abc letter.
//

#include <string.h>
#include <stdio.h>

int main( void )
{
   char string[] = "cabbage";
   int  result;
   result = strspn( string, "abc" );
   printf( "The portion of '%s' containing only a, b, or c "
           "is %d bytes long\n", string, result );
}
```

```Output
The portion of 'cabbage' containing only a, b, or c is 5 bytes long
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_strspnp, _wcsspnp, _mbsspnp, _mbsspnp_l](strspnp-wcsspnp-mbsspnp-mbsspnp-l.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
