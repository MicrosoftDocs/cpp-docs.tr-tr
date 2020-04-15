---
title: _strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l
ms.date: 4/2/2020
api_name:
- _mbsnbcnt_l
- _mbsnccnt
- _wcsncnt
- _strncnt
- _mbsnccnt_l
- _mbsnbcnt
- _o__mbsnbcnt
- _o__mbsnbcnt_l
- _o__mbsnccnt
- _o__mbsnccnt_l
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: bfd339a38dd5df30ece72059525860603ee10748
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364178"
---
# <a name="_strncnt-_wcsncnt-_mbsnbcnt-_mbsnbcnt_l-_mbsnccnt-_mbsnccnt_l"></a>_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l

Belirtilen sayımda karakter veya bayt sayısını verir.

> [!IMPORTANT]
> **windows**runtime'da çalışan uygulamalarda **_mbsnbcnt, _mbsnbcnt_l,** **_mbsnccnt**ve **_mbsnccnt_l** kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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

*Str*<br/>
String incelenecek.

*Sayısı*<br/>
*Str'de*incelenecek karakter veya bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

**_mbsnbcnt** ve **_mbsnbcnt_l** *str*multibayt karakterlerinin ilk *sayısında* bulunan bayt sayısını döndürün. **_mbsnccnt** ve **_mbsnccnt_l** *str*baytilk *sayısında* bulunan karakter sayısını döndürün. *Str'in* muayenesi tamamlanmadan önce null bir karakterle karşılaşılırsa, null karakterden önce bulunan bayt veya karakter sayısını döndürer. *Str,* *sayım* karakterlerinden veya baytlardan daha az karakterden oluşuyorsa, dizedeki karakter veya bayt sayısını döndürer. *Sayım* sıfırdan azsa, 0 döndürülür. Önceki sürümlerde, bu işlevler **size_t**yerine tür **int** bir dönüş değeri vardı.

**_strncnt** tek bayt dize *str*ilk *sayısı* bayt karakter sayısını döndürür. **_wcsncnt** geniş karakterli dize *str*ilk *sayısı* geniş karakter karakter sayısını döndürür.

## <a name="remarks"></a>Açıklamalar

**_mbsnbcnt** ve **_mbsnbcnt_l** *str*multibayt karakterlerinin ilk *sayısında* bulunan bayt sayısını saymak. **_mbsnbcnt** ve **_mbsnbcnt_l** **mtob** yerine kullanılmalıdır ve **mtob**yerine kullanılmalıdır.

**_mbsnccnt** ve **_mbsnccnt_l** *str*baytilk *sayısında* bulunan karakter sayısını saymak. **_mbsnccnt** ve **_mbsnccnt_l** çift bayt karakterin ikinci baytında null bir karakterle karşılaşırsa, ilk bayt da null olarak kabul edilir ve döndürülen sayım değerine dahil edilmez. **_mbsnccnt** ve **_mbsnccnt_l** **btom** yerine ve **btom**yerine kullanılmalıdır.

*Str* bir **NULL** işaretçisi yse veya *sayı* 0 ise, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır, **errno** **EINVAL**olarak ayarlanır ve işlev 0 döndürür.

Çıktı değeri, yerel LC_CTYPE **kategori** ayarı ayarı etkilenir; daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md) bakın. Bu işlevlerin **_l** soneki olmayan sürümleri, bu yerele bağımlı davranış için geçerli yerel durumu kullanır; **_l** soneki olan sürümler, bunun yerine geçirilen yerel parametreyi kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Yordam|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|-------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnbcnt**|**_strncnt**|**_mbsnbcnt**|**_wcsncnt**|
|**_tcsnccnt**|**_strncnt**|**_mbsnbcnt**|yok|
|**_wcsncnt**|yok|yok|**_mbsnbcnt**|
|**_wcsncnt**|yok|yok|**_mbsnccnt**|
|yok|yok|**_mbsnbcnt_l**|**_mbsnccnt_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbcnt**|\<mbstring.h>|
|**_mbsnbcnt_l**|\<mbstring.h>|
|**_mbsnccnt**|\<mbstring.h>|
|**_mbsnccnt_l**|\<mbstring.h>|
|**_strncnt**|\<tchar.h>|
|**_wcsncnt**|\<tchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

### <a name="output"></a>Çıktı

```Output
The first 10 characters are single-byte.
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
