---
title: _strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l
ms.date: 11/04/2016
api_name:
- _mbsnbcnt_l
- _mbsnccnt
- _wcsncnt
- _strncnt
- _mbsnccnt_l
- _mbsnbcnt
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
- api-ms-win-crt-multibyte-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbsnbcnt
- wcsncnt
- _tcsnbcnt
- _mbsnccnt
- _ftcsnbcnt
- mbsnbcnt
- strncnt
- mbsnbcnt_l
- mbsnccnt_l
- mbsnccnt
- _strncnt
- _wcsncnt
helpviewer_keywords:
- _strncnt function
- _mbsnbcnt function
- _mbsnbcnt_l function
- _mbsnccnt_l function
- mbsnbcnt_l function
- mbsnbcnt function
- tcsnbcnt function
- mbsnccnt_l function
- strncnt function
- _tcsnbcnt function
- mbsnccnt function
- wcsncnt function
- _mbsnccnt function
- _wcsncnt function
ms.assetid: 2a022e9e-a307-4acb-a66b-e56e5357f848
ms.openlocfilehash: 4c00ae3ff845dfbc3daf4a3ea6ce5c34c43e475f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70947307"
---
# <a name="_strncnt-_wcsncnt-_mbsnbcnt-_mbsnbcnt_l-_mbsnccnt-_mbsnccnt_l"></a>_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l

Belirtilen bir Count içindeki karakter veya bayt sayısını döndürür.

> [!IMPORTANT]
> **_mbsnbcnt**, **_mbsnbcnt_l**, **_mbsnccnt**ve **_mbsnccnt_l** Windows çalışma zamanı içinde yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
size_t _strncnt(
   const char *str,
   size_t count
);
size_t _wcsncnt(
   const wchar_t *str,
   size_t count
);
size_t _mbsnbcnt(
   const unsigned char *str,
   size_t count
);
size_t _mbsnbcnt_l(
   const unsigned char *str,
   size_t count,
   _locale_t locale
);
size_t _mbsnccnt(
   const unsigned char *str,
   size_t count
);
size_t _mbsnccnt_l(
   const unsigned char *str,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
İncelenme dizesi.

*biriktirme*<br/>
*Str*içinde İncelenme karakter veya bayt sayısı.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbsnbcnt** ve **_mbsnbcnt_l** , *Str*çok baytlı karakterlerinin ilk *sayısında* bulunan bayt sayısını döndürür. **_mbsnccnt** ve **_mbsnccnt_l** , *Str*'nin ilk bayt *sayısında* bulunan karakter sayısını döndürür. *Str* incelemesi tamamlanmadan null karakter ile karşılaşılırsa, null karakterden önce bulunan bayt veya karakter sayısını döndürür. *Str* *sayı* sayısından az karakter veya bayttan oluşuyorsa, dizedeki karakter veya bayt sayısını döndürür. *Count* değeri sıfırdan küçükse 0 döndürür. Önceki sürümlerde, bu işlevlerde **size_t**yerine **int** türünde bir dönüş değeri vardı.

**_strncnt** , tek baytlık dize *Str*'nin ilk *sayım* baytındaki karakter sayısını döndürür. **_wcsnsayisi** , geniş karakterli dize *Str*'nin ilk *sayı* geniş karakterdeki karakter sayısını döndürür.

## <a name="remarks"></a>Açıklamalar

**_mbsnbcnt** ve **_mbsnbcnt_l** Count *dize*çok baytlı karakterlerinin ilk *sayısında* bulunan bayt sayısı. **_mbsnbcnt** ve **_mbsnbcnt_l** , **mtob** 'yi değiştirip **mtob**yerine kullanılmalıdır.

**_mbsnccnt** ve **_mbsnccnt_l** Count ilk *Str*bayt *sayısı* içinde bulunan karakter sayısı. **_Mbsnccnt** ve **_mbsnccnt_l** , çift baytlık bir karakterin ikinci baytında null bir karakterle karşılaştığında, ilk bayt de null olarak kabul edilir ve döndürülen sayı değerine dahil değildir. **_mbsnccnt** ve **_mbsnccnt_l** **bTom** yerini alır ve **bTom**'ın yerine kullanılmalıdır.

*Str* **null** bir işaretçisiyse veya *sayı* 0 ise, bu işlevler [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır, **errno** , **EINVAL**olarak ayarlanır ve işlev 0 döndürür.

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md) . **_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip sürümler, bunun yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Yordam|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|-------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnbcnt**|**_strncnt**|**_mbsnbcnt**|**_wcsnsayisi**|
|**_tcsnccnt**|**_strncnt**|**_mbsnbcnt**|yok|
|**_wcsnsayisi**|yok|yok|**_mbsnbcnt**|
|**_wcsnsayisi**|yok|yok|**_mbsnccnt**|
|yok|yok|**_mbsnbcnt_l**|**_mbsnccnt_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbcnt**|\<mbstring. h >|
|**_mbsnbcnt_l**|\<mbstring. h >|
|**_mbsnccnt**|\<mbstring. h >|
|**_mbsnccnt_l**|\<mbstring. h >|
|**_strncnt**|\<Tchar. h >|
|**_wcsnsayisi**|\<Tchar. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_mbsnbcnt.c

#include  <mbstring.h>
#include  <stdio.h>

int main( void )
{
   unsigned char str[] = "This is a multibyte-character string.";
   unsigned int char_count, byte_count;
   char_count = _mbsnccnt( str, 10 );
   byte_count = _mbsnbcnt( str, 10 );
   if ( byte_count - char_count )
      printf( "The first 10 characters contain %d multibyte characters\n", char_count );
   else
      printf( "The first 10 characters are single-byte.\n");
}
```

### <a name="output"></a>Çıkış

```Output
The first 10 characters are single-byte.
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenleme](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
