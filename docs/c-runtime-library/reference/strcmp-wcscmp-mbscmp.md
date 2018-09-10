---
title: strcmp, wcscmp, _mbscmp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcscmp
- _mbscmp
- strcmp
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _mbscmp
- wcscmp
- strcmp
- _tcscmp
- _ftcscmp
dev_langs:
- C++
helpviewer_keywords:
- tcscmp function
- strcmp function
- strings [C++], comparing
- mbscmp function
- string comparison [C++]
- _mbscmp function
- wcscmp function
- _tcscmp function
- _ftcscmp function
- ftcscmp function
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca1591bba9518b1b5f6122f51bf60f5a23fc7a26
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44319012"
---
# <a name="strcmp-wcscmp-mbscmp"></a>strcmp, wcscmp, _mbscmp

Dizeleri karşılaştırır.

> [!IMPORTANT]
> **_mbscmp** Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int strcmp(
   const char *string1,
   const char *string2
);
int wcscmp(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbscmp(
   const unsigned char *string1,
   const unsigned char *string2
);
```

### <a name="parameters"></a>Parametreler

*Dize1*, *dize2*<br/>
Karşılaştırmak için null ile sonlandırılmış dizeler.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri için dönüş değeri sıralı ilişkisi gösterir *Dize1* için *dize2*.

|Değer|Dize1 dize2 ile ilişkisi|
|-----------|----------------------------------------|
|< 0|*Dize1* olduğu küçüktür *dize2*|
|0|*Dize1* aynıdır *dize2*|
|> 0|*Dize1* büyüktür *dize2*|

Parametre doğrulama hata **_mbscmp** döndürür **_NLSCMPERROR**, tanımlanan \<string.h > ve \<mbstring.h >.

## <a name="remarks"></a>Açıklamalar

**Strcmp** işlevi, sıralı bir karşılaştırma gerçekleştirir *Dize1* ve *dize2* ve ilişkilerini gösteren bir değer döndürür. **wcscmp** ve **_mbscmp** , sırasıyla, geniş karakter ve çok baytlı karakter sürümleridir **strcmp**. **_mbscmp** geçerli çok baytlı kod sayfasına göre çok baytlı karakter dizileri tanır ve döndürür **_NLSCMPERROR** üzerinde hata. Daha fazla bilgi için [kod sayfaları](../../c-runtime-library/code-pages.md). Ayrıca, varsa *Dize1* veya *dize2* null bir işaretçiyse, **_mbscmp** açıklandığı gibi geçersiz parametre işleyicisini çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **_mbscmp** döndürür **_NLSCMPERROR** ve ayarlar **errno** için **EINVAL**. **strcmp** ve **wcscmp** kendi parametrelerini doğrulamazlar. Bu üç işlev aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscmp**|**strcmp**|**_mbscmp**|**wcscmp**|

**Strcmp** işlevleri tümünden **strcoll** , İşlevler **strcmp** karşılaştırmaları sıralı ve yerel ayar tarafından etkilenmez. **strcoll** lexicographically kullanarak dizeleri karşılaştırır **LC_COLLATE** geçerli yerel ayarının kategori. Hakkında daha fazla bilgi için **LC_COLLATE** kategori bkz [setlocale, _wsetlocale](setlocale-wsetlocale.md).

"C" yerel ayarında (ASCII karakter kümesi) karakter kümesindeki karakterlerin sırası sözlük karakter sırası ile aynıdır. Ancak, başka yerel ayarlara karakter kümesindeki karakterlerin sırası sözlük sırasından farklı olabilir. Örneğin, Avrupa belirli yerlerde karakter 'a' (değer 0x61) önceki karakteri 'ä' (değer 0xE4) karakter kümesi, ancak 'ä' gelen karakterin önüne karakter gelir 'bir' lexicographically.

Kendisi için karakter kümesi ve lexicographic karakter sırası farklı yerlerde kullandığınız **strcoll** yerine **strcmp** lexicographic karşılaştırmasını dizeleri için. Alternatif olarak, **strxfrm** özgün dizeleri ve ardından **strcmp** elde edilen dizeler.

**Strcmp** işlevleri duyarlıdır. **_stricmp**, **_wcsicmp**, ve **_mbsicmp** ilk bunları küçük formlarına dönüştürerek dizeleri karşılaştırır. Bulunduğu 'Z' arasında karakterler içeren iki dizeyi ASCII tablosunda ' bir ' ('[','\\', ']', ' ^', '_' ve '\`') bağlı olarak farklı şekilde karşılaştırın. Örneğin, iki "ABCDE" dizeleri ve "ABCD ^" karşılaştırma küçük harf ise tek yolla karşılaştırılır ("abcde" > "abcd ^") ve başka bir yolla ("ABCDE" < "ABCD ^") karşılaştırma büyük harf ise.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strcmp**|\<String.h >|
|**wcscmp**|\<String.h > veya \<wchar.h >|
|**_mbscmp**|\<Mbstring.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_strcmp.c

#include <string.h>
#include <stdio.h>
#include <stdlib.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown dog jumps over the lazy fox";

int main( void )
{
   char tmp[20];
   int result;

   // Case sensitive
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );
   result = strcmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );

   // Case insensitive (could use equivalent _stricmp)
   result = _stricmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof (tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );
}
```

```Output
Compare strings:
   The quick brown dog jumps over the lazy fox
   The QUICK brown dog jumps over the lazy fox

   strcmp:   String 1 is greater than string 2
   _stricmp:  String 1 is equal to string 2
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[_memicmp, _memicmp_l](memicmp-memicmp-l.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
