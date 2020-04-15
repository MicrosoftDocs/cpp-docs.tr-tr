---
title: _strupr_s, _strupr_s_l, _mbsupr_s, _mbsupr_s_l, _wcsupr_s, _wcsupr_s_l
ms.date: 4/2/2020
api_name:
- _strupr_s
- _strupr_s_l
- _mbsupr_s
- _wcsupr_s_l
- _mbsupr_s_l
- _wcsupr_s
- _o__mbsupr_s
- _o__mbsupr_s_l
- _o__strupr_s
- _o__strupr_s_l
- _o__wcsupr_s
- _o__wcsupr_s_l
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strupr_s
- mbsupr_s
- wcsupr_s
- _mbsupr_s_l
- mbsupr_s_l
- wcsupr_s_l
- _wcsupr_s
- _tcsupr_s_l
- _mbsupr_s
- _tcsupr_s
- strupr_s_l
- _wcsupr_s_l
- _strupr_s
- _strupr_s_l
helpviewer_keywords:
- mbsupr_s_l function
- strupr_s_l function
- _wcsupr_s_l function
- _tcsupr_s_l function
- mbsupr_s function
- _wcsupr_s function
- uppercase, converting strings to
- tcsupr_s function
- string conversion [C++], case
- strupr_s function
- wcsupr_s_l function
- _mbsupr_s function
- _mbsupr_s_l function
- _strupr_s_l function
- tcsupr_s_l function
- strings [C++], case
- converting case, CRT functions
- _tcsupr_s function
- strings [C++], converting case
- _strupr_s function
- wcsupr_s function
ms.assetid: 82d3a273-9f6f-4a26-9560-919d891e4581
ms.openlocfilehash: 2fd90f462787df739f41a9e8e10f84d2fc52c456
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362981"
---
# <a name="_strupr_s-_strupr_s_l-_mbsupr_s-_mbsupr_s_l-_wcsupr_s-_wcsupr_s_l"></a>_strupr_s, _strupr_s_l, _mbsupr_s, _mbsupr_s_l, _wcsupr_s, _wcsupr_s_l

Geçerli yerel alanı veya geçirilen belirli bir yerel alanı kullanarak bir dizeyi büyük harfe dönüştürür. [_strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l _wcsupr](strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md) bu [sürümlerinde CRT'deki Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmeleri vardır.

> [!IMPORTANT]
> **_mbsupr_s** ve **_mbsupr_s_l,** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _strupr_s(
   char *str,
   size_t numberOfElements
);
errno_t _wcsupr_s(
   wchar_t * str,
   size_t numberOfElements
);
errno_t _strupr_s_l(
   char * str,
   size_t numberOfElements,
   _locale_t locale
);
errno_t _wcsupr_s_l(
   wchar_t * str,
   size_t numberOfElements,
   _locale_t locale
);
errno_t _mbsupr_s(
   unsigned char *str,
   size_t numberOfElements
);
errno_t _mbsupr_s_l(
   unsigned char *str,
   size_t numberOfElements,
   _locale_t locale
);
template <size_t size>
errno_t _strupr_s(
   char (&str)[size]
); // C++ only
template <size_t size>
errno_t _wcsupr_s(
   wchar_t (&str)[size]
); // C++ only
template <size_t size>
errno_t _strupr_s_l(
   char (&str)[size],
   _locale_t locale
); // C++ only
template <size_t size>
errno_t _wcsupr_s_l(
   wchar_t (&str)[size],
   _locale_t locale
); // C++ only
template <size_t size>
errno_t _mbsupr_s(
   unsigned char (&str)[size]
); // C++ only
template <size_t size>
errno_t _mbsupr_s_l(
   unsigned char (&str)[size],
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Büyük harfe bağlaç.

*numberOfElements*<br/>
Arabelleğe boyutu.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır; hatası olmayan bir hata kodu.

Bu işlevler parametrelerini doğrular. *Str* bir **NULL** işaretçisiise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, işlevleri **EINVAL** dönmek ve **EINVAL** **için errno** ayarlayın. *NumberOfElements* dize uzunluğundan daha az ise, işlevler **ERANGE** döndürün ve **ERANGE** **için errno** ayarlayın.

## <a name="remarks"></a>Açıklamalar

**_strupr_s** işlevi, yerinde, *büyük* harf str her küçük harf dönüştürür. **_wcsupr_s** **_strupr_s**geniş karakterli sürümüdür. **_mbsupr_s** **_strupr_s**çok bayt karakter sürümüdür.

Dönüştürme, LC_CTYPE **kategori** ayarına göre belirlenir. Diğer karakterler etkilenmez. **LC_CTYPE**hakkında daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md)bakın. Bu işlevlerin **_l** sonek olmadan sürümleri geçerli yerel kullanın; **_l** soneki ile vizyonları yerine geçirilen yerel kullanmak dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkartabilir (boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir) ve eski, güvenli olmayan işlevleri yeni, güvenli karşılıklarıyla otomatik olarak değiştirebilirler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Bu işlevlerin hata ayıklama kitaplığı sürümleri önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsupr_s**|**_strupr_s**|**_mbsupr_s**|**_wcsupr_s**|
|**_tcsupr_s_l**|**_strupr_s_l**|**_mbsupr_s_l**|**_wcsupr_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strupr_s**, **_strupr_s_l**|\<string.h>|
|**_wcsupr_s**, **_wcsupr_s_l**, **_mbsupr_s**, **_mbsupr_s_l**|\<string.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[_strlwr_s, _strlwr_s_l, _mbslwr_s, _mbslwr_s_l, _wcslwr_s, _wcslwr_s_l](strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md) örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strlwr_s, _strlwr_s_l, _mbslwr_s, _mbslwr_s_l, _wcslwr_s, _wcslwr_s_l](strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)<br/>
