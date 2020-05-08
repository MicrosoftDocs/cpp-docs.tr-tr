---
title: _mbccpy_s, _mbccpy_s_l
ms.date: 4/2/2020
api_name:
- _mbccpy_s
- _mbccpy_s_l
- _o__mbccpy_s
- _o__mbccpy_s_l
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 85db4e478b070823bb14028018d918e0f3cabbd7
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920316"
---
# <a name="_mbccpy_s-_mbccpy_s_l"></a>_mbccpy_s, _mbccpy_s_l

Bir dizeden başka bir dizeye bir çok baytlı karakter kopyalar. Bu _mbccpy sürümleri [, _MBCCPY_L](mbccpy-mbccpy-l.md) [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri içerir.

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

*src*<br/>
Kopyalanacak çok baytlı karakter.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatada hata kodu. *Src* veya *dest* **null**ise veya **BuffSizeinBytes** bayttan fazlası *hedefe*kopyalanacaksa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlevler **EINVAL** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**_Mbccpy_s** işlevi bir çok baytlı karakteri *src* 'den *hedefe*kopyalar. *Src* , [_ismbblead](ismbblead-ismbblead-l.md)örtük çağrısıyla belirlendiği şekilde çok baytlı bir karakterin ön bayta işaret ediyorsa, *src* 'nin gösterdiği tek bayt kopyalanır. *Src* bir ön bayta işaret ediyorsa, ancak aşağıdaki bayt 0 ' dır ve bu nedenle geçersiz olursa, 0 *hedefe*kopyalanır, **errno** **Eilseq**olarak ayarlanır ve işlev **eilseq**' i döndürür.

**_mbccpy_s** , null Sonlandırıcı eklemez; Ancak, *src* bir null karaktere işaret ediyorsa, bu null *hedefe* kopyalanır (Bu yalnızca normal bir tek baytlık kopyasıdır).

*Pkopyalanmakta* olan değer, kopyalanmış bayt sayısıyla doldurulmuştur. İşlem başarılı olursa olası değerler 1 ve 2 ' dir. **Null** değer geçirilirse, bu parametre yoksayılır.

|*src*|*hedefe* kopyalanmış|*Pkopyalanmıyor*|Döndürülen değer|
|-----------|----------------------|---------------|------------------|
|ön bayt olmayan|ön bayt olmayan|1|0|
|0|0|1|0|
|ön bayt ve ardından 0 olmayan|ön bayt ve ardından 0 olmayan|2|0|
|ön bayt izleyen 0|0|1|**EıLSEQ**|

İkinci satırın yalnızca ilk olarak özel bir durum olduğunu unutmayın. Ayrıca tablonun *buffSizeInBytes* >= *pkopyalanmış*olduğunu varsaydığını unutmayın.

**_mbccpy_s** , yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_mbccpy_s_l** , **_mbccpy_s** bir yerel ayara bağımlı davranış için geçirilen yerel ayarı kullanması dışında, **_mbccpy_s_l** aynıdır.

C++ ' da, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir ve bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy_s**|Makro veya satır içi işlev ile eşlenir.|**_mbccpy_s**|Makro veya satır içi işlev ile eşlenir.|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbccpy_s**|\<mbstring. h>|
|**_mbccpy_s_l**|\<mbstring. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
