---
title: _strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l
ms.date: 4/2/2020
api_name:
- _wcsset
- _mbsset
- _strset_l
- _strset
- _wcsset_l
- _mbsset_l
- _o__mbsset
- _o__mbsset_l
- _o__wcsset
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbsset
- _strset_l
- _mbsset
- _strset
- mbsset_l
- strset_l
- _wcsset
- _ftcsset
- wcsset_l
- _tcsset_l
- _mbsset_l
- _wcsset_l
- _fstrset
- _tcsset
helpviewer_keywords:
- _wcsset_l function
- _tcsset function
- wcsset_l function
- _ftcsset function
- characters [C++], setting
- _strset function
- ftcsset function
- strings [C++], setting characters
- mbsset function
- tcsset_l function
- _fstrset function
- mbsset_l function
- strset_l function
- _wcsset function
- _mbsset function
- _mbsset_l function
- tcsset function
- _strset_l function
- fstrset function
- _tcsset_l function
ms.assetid: c42ded42-2ed9-4f06-a0a9-247ba305473a
ms.openlocfilehash: 304f0cf5929dcce68402dd2f7dc2ce3b28e36db9
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911120"
---
# <a name="_strset-_strset_l-_wcsset-_wcsset_l-_mbsset-_mbsset_l"></a>_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l

Bir dizenin karakterlerini bir karaktere ayarlar. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [_strset_s, _strset_s_l, _wcsset_s, _wcsset_s_l, _mbsset_s, _mbsset_s_l](strset-s-strset-s-l-wcsset-s-wcsset-s-l-mbsset-s-mbsset-s-l.md).

> [!IMPORTANT]
> **_mbsset** ve **_mbsset_l** , Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
char *_strset(
   char *str,
   int c
);
char *_strset_l(
   char *str,
   int c,
   locale_t locale
);
wchar_t *_wcsset(
   wchar_t *str,
   wchar_t c
);
wchar_t *_wcsset_l(
   wchar_t *str,
   wchar_t c,
   locale_t locale
);
unsigned char *_mbsset(
   unsigned char *str,
   unsigned int c
);
unsigned char *_mbsset_l(
   unsigned char *str,
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
Ayarlanacak null ile sonlandırılmış dize.

*,*<br/>
Karakter ayarı.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Değiştirilen dizeye bir işaretçi döndürür.

## <a name="remarks"></a>Açıklamalar

**_Strset** işlevi, *Str* 'den *c*'ye dönüştürülen tüm karakterleri (yani Sonlandırıcı null karakteri hariç) **belirler.** **_wcsset** ve **_mbsset_l** , **_strset**geniş karakter ve çok baytlı karakter sürümleridir ve bağımsız değişkenlerin ve dönüş değerlerinin veri türleri buna göre farklılık gösterir. Bu işlevler, aynı şekilde davranır.

**_mbsset** parametrelerini doğrular. *Str* null Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa **_Mbsset** **null** değerini döndürür ve **errno** 'ı **EINVAL**olarak ayarlar. **_strset** ve **_wcsset** parametrelerini doğrulamaz.

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md) . Bu işlevlerin sürümleri aynıdır, çünkü **_l** sonekine sahip olmayanlar geçerli yerel ayarı kullanır, bunun yerine **_l** sonekine sahip olanlar, geçirilen yerel ayar parametresini kullanır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

> [!IMPORTANT]
> Bu işlevler, arabellek taşma tehditlerine karşı savunmasız olabilir. Arabellek taşmaları, sistem saldırıları için kullanılabilir ve bu ayrıcalıklar ayrıcalık yükselmesine neden olabilir. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsset**|**_strset**|**_mbsset**|**_wcsset**|
|**_tcsset_l**|**_strset_l**|**_mbsset_l**|**_wcsset_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strset**|\<String. h>|
|**_strset_l**|\<Tchar. h>|
|**_wcsset**|\<String. h> veya \<wchar. h>|
|**_wcsset_l**|\<Tchar. h>|
|**_mbsset**, **_mbsset_l**|\<mbstring. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strset.c
// compile with: /W3

#include <string.h>
#include <stdio.h>

int main( void )
{
   char string[] = "Fill the string with something.";
   printf( "Before: %s\n", string );
   _strset( string, '*' ); // C4996
   // Note: _strset is deprecated; consider using _strset_s instead
   printf( "After:  %s\n", string );
}
```

```Output
Before: Fill the string with something.
After:  *******************************
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbset, _mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)<br/>
