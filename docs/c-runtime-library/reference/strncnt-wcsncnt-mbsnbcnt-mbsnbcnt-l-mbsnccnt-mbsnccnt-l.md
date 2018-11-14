---
title: _strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l
ms.date: 11/04/2016
apiname:
- _mbsnbcnt_l
- _mbsnccnt
- _wcsncnt
- _strncnt
- _mbsnccnt_l
- _mbsnbcnt
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
apitype: DLLExport
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
ms.openlocfilehash: 456a11ae98fe8fb40c2ef1d6f4e6d86583f4b7b3
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51520220"
---
# <a name="strncnt-wcsncnt-mbsnbcnt-mbsnbcntl-mbsnccnt-mbsnccntl"></a>_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l

Belirli bir sayım içindeki karakter veya bayt sayısını döndürür.

> [!IMPORTANT]
> **_mbsnbcnt**, **_mbsnbcnt_l**, **_mbsnccnt**, ve **_mbsnccnt_l** Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*str*<br/>
İncelenecek dize.

*Sayısı*<br/>
Karakter veya içinde incelenecek bayt sayısını *str*.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbsnbcnt** ve **_mbsnbcnt_l** bulunan bayt sayısını Döndür ilk *sayısı* çok baytlı karakter sayısını *str*. **_mbsnccnt** ve **_mbsnccnt_l** bulunan karakter sayısını döndürür ilk *sayısı* bayt sayısı *str*. Bir null karakter incelenmesi önce karşılaşılırsa *str* sahip tamamlandı, null karakterden önce bulunan karakter veya bayt sayısını döndürürler. Varsa *str* daha azından oluşuyorsa *sayısı* karakter veya bayt, döndürmeleri karakter veya bayt sayısı dizedeki. Varsa *sayısı* küçük sıfırdan, 0 döndürürler. Önceki sürümlerde, bu işlevlerin bir dönüş değeri olduğu **int** yerine **size_t**.

**_strncnt** ilk karakter sayısını döndürür *sayısı* tek baytlık dizeyi baytını *str*. **_wcsncnt** ilk karakter sayısını döndürür *sayısı* geniş karakter dizesinin geniş karakterler *str*.

## <a name="remarks"></a>Açıklamalar

**_mbsnbcnt** ve **_mbsnbcnt_l** bulunan bayt sayısını ilk *sayısı* çok baytlı karakter sayısını *str*. **_mbsnbcnt** ve **_mbsnbcnt_l** değiştirin **mtob** ve yerine kullanılması gereken **mtob**.

**_mbsnccnt** ve **_mbsnccnt_l** bulunan karakter sayısını ilk *sayısı* bayt sayısı *str*. Varsa **_mbsnccnt** ve **_mbsnccnt_l** çift baytlı bir karakterin ikinci baytında bir null karakter karşılaşırsanız, ilk bayt da null olarak kabul edilir ve döndürülen sayı değerine dahil değildir. **_mbsnccnt** ve **_mbsnccnt_l** değiştirin **btom** ve yerine kullanılması gereken **btom**.

Varsa *str* olduğu bir **NULL** işaretçi veya *sayısı* 0'dır, bu işlevler içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md), **errno** ayarlanır **EINVAL**, ve işlev 0 döndürür.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı kullanır bu yerel ayara bağlı davranışı için; sürümleriyle **_l** sonekine bunların yerel ayar parametresini kullanmalarıdır Bunun yerine iletilmiş. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

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
|**_mbsnbcnt**|\<Mbstring.h >|
|**_mbsnbcnt_l**|\<Mbstring.h >|
|**_mbsnccnt**|\<Mbstring.h >|
|**_mbsnccnt_l**|\<Mbstring.h >|
|**_strncnt**|\<Tchar.h >|
|**_wcsncnt**|\<Tchar.h >|

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

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
