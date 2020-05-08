---
title: strcmp, wcscmp, _mbscmp, _mbscmp_l
ms.date: 4/2/2020
api_name:
- wcscmp
- _mbscmp
- _mbscmp_l
- strcmp
- _o__mbscmp
- _o__mbscmp_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbscmp
- _mbscmp_l
- wcscmp
- strcmp
- _tcscmp
- _ftcscmp
helpviewer_keywords:
- tcscmp function
- strcmp function
- strings [C++], comparing
- mbscmp function
- string comparison [C++]
- _mbscmp function
- _mbscmp_l function
- wcscmp function
- _tcscmp function
- _ftcscmp function
- ftcscmp function
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
ms.openlocfilehash: 805e355fe12cb2f7ead6180edd45ad0748570141
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920389"
---
# <a name="strcmp-wcscmp-_mbscmp-_mbscmp_l"></a>strcmp, wcscmp, _mbscmp, _mbscmp_l

Dizeleri karşılaştırın.

> [!IMPORTANT]
> **_mbscmp** ve **_mbscmp_l** , Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
int _mbscmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Dize1*, *dize2*<br/>
Karşılaştırılacak null ile sonlandırılmış dizeler.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri için dönüş değeri, *Dize1* ile *dize2*arasındaki sıralı ilişkiyi belirtir.

|Değer|Dize1 ile dize2 arasındaki ilişki|
|-----------|----------------------------------------|
|< 0|*Dize1* *dize2* 'den küçük|
|0|*Dize1* *dize2* ile aynıdır|
|> 0|*Dize1* *dize2* 'den büyük|

Bir parametre doğrulama hatası üzerinde **_mbscmp** ve **_mbscmp_l** String. h> ve \<mbstring. \<h> içinde tanımlanan **_NLSCMPERROR**döndürün.

## <a name="remarks"></a>Açıklamalar

**Strcmp** işlevi, *Dize1* ve *dize2* için sıralı bir karşılaştırma gerçekleştirir ve ilişkilerini gösteren bir değer döndürür. **wcscmp** ve **_mbscmp** , sırasıyla **strcmp**'nin geniş karakterli ve çok baytlı karakter sürümleridir. **_mbscmp** , geçerli çok baytlı kod sayfasına göre çok baytlı karakter dizilerini tanır ve bir hata üzerinde **_NLSCMPERROR** döndürür. **_mbscmp_l** aynı davranışa sahiptir, ancak geçerli yerel ayar yerine geçirilen yerel ayar parametresini kullanır. Daha fazla bilgi için bkz. [kod sayfaları](../../c-runtime-library/code-pages.md). Ayrıca, *Dize1* veya *dize2* null Işaretçisiyse, **_mbscmp** [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, **_mbscmp** ve **_mbscmp_l** **_NLSCMPERROR** döndürün ve **errno** öğesini **EINVAL**olarak ayarlayın. **strcmp** ve **wcscmp** parametrelerini doğrulamaz. Bu işlevler, aynı şekilde davranır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscmp**|**strcmp**|**_mbscmp**|**wcscmp**|

**Strcmp işlevleri,** **strcmp** karşılaştırmalarının sıralı olduğu ve yerel ayardan etkilenmedikleri **strcoll** işlevlerinden farklıdır. **strcoll** , geçerli yerel ayarın **LC_COLLATE** kategorisini kullanarak lexıgrafik dizelerini karşılaştırır. **LC_COLLATE** kategorisi hakkında daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md).

"C" yerel ayarında, karakter kümesindeki karakterlerin sırası (ASCII karakter kümesi), lexicographic karakter sıralaması ile aynıdır. Ancak, diğer yerel ayarlarda, karakter kümesindeki karakterlerin sırası lexicographic siparişinden farklı olabilir. Örneğin, bazı Avrupa yerel ayarları 'nda, ' a ' karakteri (0x61) karakter kümesindeki ' ä ' karakterinden (değer 0xE4) önceye gelir, ancak ' ä ' karakteri ' a ' lexıgrafik karakterinin önünde gelir.

Karakter kümesi ve lexicographic karakter sırasının farklı olduğu yerlerde, dizelerin lexıgrafgrafik karşılaştırması için **strcmp** yerine **strsıtıl** kullanabilirsiniz. Alternatif olarak, özgün dizelerde **strxfrm** ' i kullanabilir ve ardından elde edilen dizelerde **strcmp** ' yi kullanabilirsiniz.

**Strcmp** işlevleri büyük/küçük harfe duyarlıdır. stricmp, ** \_wcsıcmp**ve ** \_mbsıcmp** , önce bunları küçük formlarına dönüştürerek dizeleri karşılaştırın. ** \_** ASCII tablosunda (' [', '\\', '] ', ' ^ ', ' _ ' ve '\`') ' Z ' ve ' a ' arasında bulunan karakterler içeren iki dize, durumlarına bağlı olarak farklı şekilde karşılaştırın. Örneğin, "ABCDE" ve "ABCD ^" dizeleri, karşılaştırma küçük harfli ("ABCDE" > "abcd ^") ve diğer şekilde ("ABCDE" < "abcd ^") büyük harfli bir şekilde karşılaştırın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strcmp**|\<String. h>|
|**wcscmp**|\<String. h> veya \<wchar. h>|
|**_mbscmp**|\<mbstring. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[_memicmp, _memicmp_l](memicmp-memicmp-l.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
