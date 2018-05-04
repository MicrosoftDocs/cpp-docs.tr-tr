---
title: _mbccpy_s, _mbccpy_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a3a52314209b62c818623e315757dcd358ec491
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="mbccpys-mbccpysl"></a>_mbccpy_s, _mbccpy_s_l

Tek baytlı karakter başka bir dizeye bir dizeden kopyalar. Bu sürümleri [_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Hedef kopyalayın.

*buffSizeInBytes*<br/>
Hedef arabellek boyutu.

*pCopied*<br/>
Bayt kopyalanan (1 veya 2 başarılı olursa) sayısı ile doldurulur. Geçirmek **NULL** numarası hakkında önemli değil durumunda.

*src*<br/>
Kopyalamak için birden çok baytlı karakter.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatasında bir hata kodu. Varsa *src* veya *taşınmaya* olan **NULL**, ya da birden fazla **buffSizeinBytes** bayt için kopyalanmasına *taşınmaya*, bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır sonra [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, işlevlerin dönüş **EINVAL** ve **errno** ayarlanır **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Mbccpy_s** işlevi bir çok baytlı karakter kopyalar *src* için *taşınmaya*. Varsa *src* birden çok baytlı karakter örtük bir çağrı tarafından belirlendiği bayt göstermiyor [_ismbblead](ismbblead-ismbblead-l.md), ardından tek bayt, *src* noktalarına kopyalanır. Varsa *src* baytı ancak aşağıdaki bayt noktalarına 0 ve böylece geçersiz sonra 0 kopyalanır *taşınmaya*, **errno** ayarlanır **EILSEQ**ve işlev döndürür **EILSEQ**.

**_mbccpy_s** null Sonlandırıcı eklemediğinizden; ancak, varsa *src* bu null kopyalanır sonra bir null karakter işaret *taşınmaya* (yalnızca normal tek baytlı kopyasını budur).

Değer *pCopied* kopyalanan bayt sayısı ile doldurulur. İşlem başarılı olursa olası değerler şunlardır: 1 ve 2. Varsa **NULL** geçirilir, bu parametre yoksayılır.

|*src*|Kopyalanan *hedef*|*pCopied*|Dönüş değeri|
|-----------|----------------------|---------------|------------------|
|ön bayt|ön bayt|1.|0|
|0|0|1.|0|
|baytı-0 olmayan tarafından izlenen|baytı-0 olmayan tarafından izlenen|2|0|
|0 ve ardından ön bayt|0|1.|**EILSEQ**|

İkinci satır bir özel durum ilk olduğuna dikkat edin. Ayrıca tablo varsayar Not *buffSizeInBytes* >= *pCopied*.

**_mbccpy_s** için tüm yerel ayara bağımlı davranış geçerli yerel ayarı kullanır. **_mbccpy_s_l** aynıdır **_mbccpy_s** dışında **_mbccpy_s_l** geçirilen tüm yerel ayara bağımlı davranışını yerel ayar kullanır.

C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı, boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan arabellek uzunluğu bir otomatik olarak Infer. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy_s**|Makro veya satır içi işlev eşlenir.|**_mbccpy_s**|Makro veya satır içi işlev eşlenir.|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbccpy_s**|\<Mbstring.h >|
|**_mbccpy_s_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
