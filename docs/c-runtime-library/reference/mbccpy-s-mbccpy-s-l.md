---
title: _mbccpy_s, _mbccpy_s_l
ms.date: 11/04/2016
api_name:
- _mbccpy_s
- _mbccpy_s_l
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
ms.openlocfilehash: 26fad83c5b7847e0050fe490cad30e0643aefd74
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952627"
---
# <a name="_mbccpy_s-_mbccpy_s_l"></a>_mbccpy_s, _mbccpy_s_l

Bir dizeden başka bir dizeye bir çok baytlı karakter kopyalar. [_Mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md) 'nin bu SÜRÜMLERI, [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri içerir.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*HD*<br/>
Hedefi Kopyala.

*buffSizeInBytes*<br/>
Hedef arabelleğin boyutu.

*Pkopyalanmıyor*<br/>
Kopyalanmış bayt sayısıyla doldurulmuştur (1 veya 2 başarılıysa). Numarayı önemsemezseniz **null** geçirin.

*YN*<br/>
Kopyalanacak çok baytlı karakter.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatada hata kodu. *Src* veya *dest* **null**ise veya **BuffSizeinBytes** bayttan fazlası *hedefe*kopyalanacaksa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlevler **EINVAL** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**_Mbccpy_s** işlevi, *src* 'den *dest*'e bir çok baytlı karakter kopyalar. *Src* , [_ismbblider](ismbblead-ismbblead-l.md)için örtük bir çağrı tarafından belirlendiği şekilde çok baytlı bir karakterin ön bayta işaret ediyorsa, *src* 'nin gösterdiği tek bayt kopyalanır. *Src* bir ön bayta işaret ediyorsa, ancak aşağıdaki bayt 0 ' dır ve bu nedenle geçersiz olursa, 0 *hedefe*kopyalanır, **errno** **Eilseq**olarak ayarlanır ve işlev **eilseq**' i döndürür.

**_mbccpy_s** bir null Sonlandırıcı eklemez; Ancak, *src* bir null karaktere işaret ediyorsa, bu null *hedefe* kopyalanır (Bu yalnızca normal bir tek baytlık kopyasıdır).

*Pkopyalanmakta* olan değer, kopyalanmış bayt sayısıyla doldurulmuştur. İşlem başarılı olursa olası değerler 1 ve 2 ' dir. **Null** değer geçirilirse, bu parametre yoksayılır.

|*YN*|*hedefe* kopyalanmış|*Pkopyalanmıyor*|Dönüş değeri|
|-----------|----------------------|---------------|------------------|
|ön bayt olmayan|ön bayt olmayan|1\.|0|
|0|0|1\.|0|
|ön bayt ve ardından 0 olmayan|ön bayt ve ardından 0 olmayan|2|0|
|ön bayt izleyen 0|0|1\.|**EILSEQ**|

İkinci satırın yalnızca ilk olarak özel bir durum olduğunu unutmayın. Ayrıca tablonun *buffSizeInBytes* >= *pkopyalanmış*olduğunu varsaydığını unutmayın.

**_mbccpy_s** , yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_mbccpyı_s_l** , **_mbccpy_s** ile aynıdır, çünkü bu **_mbccpyı_s_l** , yerel ayara bağlı herhangi bir davranış için geçirilen yerel ayarı kullanır.

' C++De, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir ve bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy_s**|Makro veya satır içi işlev ile eşlenir.|**_mbccpy_s**|Makro veya satır içi işlev ile eşlenir.|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbccpy_s**|\<mbstring. h >|
|**_mbccpy_s_l**|\<mbstring. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
