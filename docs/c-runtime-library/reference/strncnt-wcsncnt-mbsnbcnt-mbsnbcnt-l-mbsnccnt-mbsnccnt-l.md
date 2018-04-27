---
title: _strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37e420754c3e534ec3518d6e4764a5366332fd96
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="strncnt-wcsncnt-mbsnbcnt-mbsnbcntl-mbsnccnt-mbsnccntl"></a>_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l

Karakter veya belirtilen sayı bayt sayısını döndürür.

> [!IMPORTANT]
> **_mbsnbcnt**, **_mbsnbcnt_l**, **_mbsnccnt**, ve **_mbsnccnt_l** Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
İncelenmesi dizesi.

*Sayısı*<br/>
Karakter veya içinde incelenmesi bayt sayısını *str*.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbsnbcnt** ve **_mbsnbcnt_l** bulunan bayt sayısını döndürmek ilk *sayısı* birden çok baytlı karakter sayısını *str*. **_mbsnccnt** ve **_mbsnccnt_l** bulunan karakter sayısını Döndür ilk *sayısı* bayt sayısı *str*. Bir NULL karakter incelenmesi önce karşılaştı, *str* sahip tamamlandı, bunlar bayt veya önce NULL karakter bulundu karakter sayısını döndürür. Varsa *str* daha az oluşan *sayısı* karakter veya bayt döndürmeleri karakter veya bayt sayısını dizesi içinde. Varsa *sayısı* küçük sıfırdan, bunlar 0 döndürür. Önceki sürümlerde, bu işlevler bir dönüş değeri olan **int** yerine **size_t**.

**_strncnt** ilk karakter sayısını verir *sayısı* bayt tek baytlı dizesinin *str*. **_wcsncnt** ilk karakter sayısını verir *sayısı* geniş karakter dizesi geniş karakterler *str*.

## <a name="remarks"></a>Açıklamalar

**_mbsnbcnt** ve **_mbsnbcnt_l** bulunan bayt sayısı ilk *sayısı* birden çok baytlı karakter sayısını *str*. **_mbsnbcnt** ve **_mbsnbcnt_l** Değiştir **mtob** ve yerine kullanılmalıdır **mtob**.

**_mbsnccnt** ve **_mbsnccnt_l** bulunan karakterleri sayma ilk *sayısı* bayt sayısı *str*. Varsa **_mbsnccnt** ve **_mbsnccnt_l** bir boş değer bir çift bayt karakter ikinci baytı karşılaşırsanız, ilk bayta kalan de NULL olarak kabul edilir ve döndürülen sayı değeri dahil edilmez. **_mbsnccnt** ve **_mbsnccnt_l** Değiştir **btom** ve yerine kullanılmalıdır **btom**.

Varsa *str* null işaretçinin veya *sayısı* 0'dır, bu işlevler açıklandığı gibi geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md), **errno** ayarlanır **EINVAL**, ve işlevi 0 değerini döndürür.

Çıkış değerini ayarı tarafından etkilenen **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; sürümleriyle **_l** soneki, yerel ayar parametresi kullanmasını dışında aynıdır Bunun yerine geçirildi. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

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

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
