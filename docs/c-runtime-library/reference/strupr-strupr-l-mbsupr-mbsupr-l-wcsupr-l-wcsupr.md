---
description: 'Hakkında daha fazla bilgi edinin: _strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr'
title: _strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr
ms.date: 4/2/2020
api_name:
- _mbsupr_l
- _mbsupr
- _strupr_l
- _wcsupr
- _wcsupr_l
- _strupr
- _o__mbsupr
- _o__mbsupr_l
- _o__strupr
- _o__strupr_l
- _o__wcsupr
- _o__wcsupr_l
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbsupr
- _ftcsupr
- mbsupr
- _tcsupr
- strupr_l
- _fstrupr
- _strupr
- mbsupr_l
- _wcsupr
helpviewer_keywords:
- tcsupr_l function
- mbsupr function
- strupr function
- uppercase, converting strings to
- wcsupr function
- _wcsupr function
- string conversion [C++], case
- ftcsupr function
- _ftcsupr function
- _wcsupr_l function
- wcsupr_l function
- strings [C++], case
- tcsupr function
- _tcsupr_l function
- _fstrupr function
- _strupr_l function
- _mbsupr_l function
- converting case, CRT functions
- fstrupr function
- mbsupr_l function
- strupr_l function
- _strupr function
- _mbsupr function
- _tcsupr function
- strings [C++], converting case
ms.assetid: caac8f16-c233-41b6-91ce-575ec7061b77
ms.openlocfilehash: a7de813f13d4a79a394ae369b4385e8e2c6e4e5a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117178"
---
# <a name="_strupr-_strupr_l-_mbsupr-_mbsupr_l-_wcsupr_l-_wcsupr"></a>_strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr

Dizeyi büyük harfe dönüştürür. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [_strupr_s, _strupr_s_l, _mbsupr_s, _mbsupr_s_l, _wcsupr_s, _wcsupr_s_l](strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md).

> [!IMPORTANT]
> **_mbsupr** ve **_mbsupr_l** , Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
char *_strupr(
   char *str
);
wchar_t *_wcsupr(
   wchar_t *str
);
unsigned char *_mbsupr(
   unsigned char *str
);
char *_strupr_l(
   char *str,
   _locale_t locale
);
wchar_t *_wcsupr_l(
   wchar_t *str,
   _locale_t locale
);
unsigned char *_mbsupr_l(
   unsigned char *str,
   _locale_t locale
);
template <size_t size>
char *_strupr(
   char (&str)[size]
); // C++ only
template <size_t size>
wchar_t *_wcsupr(
   wchar_t (&str)[size]
); // C++ only
template <size_t size>
unsigned char *_mbsupr(
   unsigned char (&str)[size]
); // C++ only
template <size_t size>
char *_strupr_l(
   char (&str)[size],
   _locale_t locale
); // C++ only
template <size_t size>
wchar_t *_wcsupr_l(
   wchar_t (&str)[size],
   _locale_t locale
); // C++ only
template <size_t size>
unsigned char *_mbsupr_l(
   unsigned char (&str)[size],
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
Büyük harfle kullanılacak dize.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Değiştirilen dizeye bir işaretçi döndürür. Değişiklik yerinde yapıldığından, döndürülen işaretçi giriş bağımsız değişkeni olarak geçirilen işaretçi ile aynıdır. Bir hatayı göstermek için hiçbir dönüş değeri ayrılmadı.

## <a name="remarks"></a>Açıklamalar

**_Strupr** işlevi, *Str* içindeki her küçük harfi de büyük harfe dönüştürür. Dönüştürme, yerel ayarın **LC_CTYPE** kategori ayarı tarafından belirlenir. Diğer karakterler etkilenmez. **LC_CTYPE** hakkında daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md). **_L** soneki olmayan bu işlevlerin sürümleri geçerli yerel ayarı kullanır; **_l** sonekine sahip sürümler, bunun yerine geçirilen yerel ayarı kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

**_wcsupr** ve **_mbsupr** , **_strupr** geniş karakter ve çok baytlı karakter sürümleridir. **_Wcsupr** bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir; **_mbsupr** olanlar çok baytlı karakter dizeleridir. Bu üç işlev, aynı şekilde davranır.

*Str* null Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md) bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler özgün dizeyi döndürür ve **errno** 'ı **EINVAL** olarak ayarlar.

C++ ' da, bu işlevlerin, bu işlevlerin daha yeni ve güvenli bir şekilde çağrılmasını sağlayan şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsupr**|**_strupr**|**_mbsupr**|**_wcsupr**|
|**_tcsupr_l**|**_strupr_l**|**_mbsupr_l**|**_wcsupr_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strupr**, **_strupr_l**|\<string.h>|
|**_wcsupr**, **_wcsupr_l**|\<string.h> veya \<wchar.h>|
|**_mbsupr**, **_mbsupr_l**|\<mbstring.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Strlwr](strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strlwr, _wcslwr, _mbslwr, _strlwr_l, _wcslwr_l, _mbslwr_l](strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md)<br/>
