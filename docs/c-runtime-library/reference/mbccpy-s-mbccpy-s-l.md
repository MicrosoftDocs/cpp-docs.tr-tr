---
title: _mbccpy_s, _mbccpy_s_l
ms.date: 11/04/2016
apiname:
- _mbccpy_s
- _mbccpy_s_l
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
- _mbccpy_s_l
- mbccpy_s_l
- mbccpy_s
- _mbccpy_s
helpviewer_keywords:
- tccpy_s_l function
- _tccpy_s function
- _mbccpy_s function
- mbccpy_s function
- tccpy_s function
- mbccpy_s_l function
- _tccpy_s_l function
- _mbccpy_s_l function
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
ms.openlocfilehash: f9a7554630bd3b46196358c01c21b99978c53e53
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156856"
---
# <a name="mbccpys-mbccpysl"></a>_mbccpy_s, _mbccpy_s_l

Çok baytlı karakteri bir dizeden başka bir dizeye kopyalar. Bu sürümleri [_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _mbccpy_s(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src
);
errno_t _mbccpy_s_l(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src,
   locale_t locale
);
template <size_t size>
errno_t _mbccpy_s(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src
); // C++ only
template <size_t size>
errno_t _mbccpy_s_l(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src,
   locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Hedef*<br/>
Hedefi kopyalayın.

*buffSizeInBytes*<br/>
Hedef arabelleğin boyutu.

*pCopied*<br/>
Bayt kopyalanan (1 veya 2 başarılı olursa) sayısı ile doldurulur. Geçirmek **NULL** sayı umursamaz durumunda.

*src*<br/>
Kopyalanacak çok baytlı karakter.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; bir hata kodu. Varsa *src* veya *dest* olduğu **NULL**, ya da daha fazlası **buffSizeinBytes** bayt kopyalanacaksa *dest*, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, İşlevler döndürür **EINVAL** ve **errno** ayarlanır **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Mbccpy_s** işlevi bir çok baytlı karakter kopyalar *src* için *dest*. Varsa *src* örtük çağrıyla tarafından belirlenen şekilde bir çok baytlı karakterin ön baytı saptandığı [_ismbblead](ismbblead-ismbblead-l.md), tek bayt, *src* kopyalanır. Varsa *src* noktalarına baytı ancak izleyen bayt 0 olduğundan geçersizse, ardından 0 kopyalanır *dest*, **errno** ayarlanır **EILSEQ**ve işlevinin döndürdükleriyle **EILSEQ**.

**_mbccpy_s** null Sonlandırıcı eklemez; ancak, *src* bu null öğesine kopyalanır null karaktere işaret *dest* (Bu, yalnızca normal tek baytlık kopya).

Değer *pCopied* , kopyalanan bayt sayısı ile doldurulur. İşlem başarılı olursa olası değerler şunlardır: 1 ve 2. Varsa **NULL** geçirilir, bu parametre yoksayılır.

|*src*|Kopyalanan *dest*|*pCopied*|Dönüş değeri|
|-----------|----------------------|---------------|------------------|
|ön bayt|ön bayt|1.|0|
|0|0|1.|0|
|ön bayt 0 olmayanla izlenir|ön bayt 0 olmayanla izlenir|2|0|
|ön bayt 0 olmayanla izlenir|0|1.|**EILSEQ**|

İkinci satırın yalnızca ilk satırın özel bir durumu olduğunu unutmayın. Ayrıca tablo varsaydığını unutmayın *buffSizeInBytes* >= *pCopied*.

**_mbccpy_s** herhangi bir yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_mbccpy_s_l** aynıdır **_mbccpy_s** dışında **_mbccpy_s_l** herhangi bir yerel ayara bağımlı davranış için geçirilen yerel ayarı kullanır.

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğu bir boyut bağımsız değişkeni belirtme gereksinimi ortadan otomatik olarak çıkarabilir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy_s**|Makro veya satır içi işleve eşlenir.|**_mbccpy_s**|Makro veya satır içi işleve eşlenir.|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbccpy_s**|\<Mbstring.h >|
|**_mbccpy_s_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
