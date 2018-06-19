---
title: _mbsnbcat_s, _mbsnbcat_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsnbcat_s_l
- _mbsnbcat_s
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
- _mbsnbcat_s
- mbsnbcat_s
- _mbsnbcat_s_l
- mbsnbcat_s_l
dev_langs:
- C++
helpviewer_keywords:
- _tcsncat function
- mbsnbcat_s function
- _mbsnbcat_s function
- _mbsnbcat_s_l function
- _tcsncat_s_l function
- tcsncat_s_l function
- mbsnbcat_s_l function
- tcsncat function
ms.assetid: 2c9e9be7-d979-4a54-8ada-23428b6648a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cead47b21a066d7e55c22d6bc8fba63cb73a0224
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405120"
---
# <a name="mbsnbcats-mbsnbcatsl"></a>_mbsnbcat_s, _mbsnbcat_s_l

Çok baytlı karakter dizesi için en fazla ilk ekler **n** bayt başka bir çok baytlı karakter dizesi. Sürümleri bunlar [_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _mbsnbcat_s(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count
);
errno_t _mbsnbcat_s_l(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t _mbsnbcat_s(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbsnbcat_s_l(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Hedef*<br/>
Çok baytlı karakter hedef null ile sonlandırılmış dize.

*sizeInBytes*<br/>
Boyutunu *taşınmaya* arabelleğinin bayt cinsinden.

*src*<br/>
Sonlandırılmış çok baytlı karakter kaynak dizesi.

*Sayısı*<br/>
Bayt sayısı *src* eklenecek *taşınmaya*.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi takdirde bir hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|**Hedef**|*sizeInBytes*|*src*|Dönüş değeri|
|------------|-------------------|-----------|------------------|
|**NULL**|tüm|tüm|**EINVAL**|
|tüm|<= 0|tüm|**EINVAL**|
|tüm|tüm|**NULL**|**EINVAL**|

Herhangi bir hata koşullarını ortaya çıkarsa, işlevi geçersiz parametre hata açıklandığı gibi oluşturuyor [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Hata durumunda işlenir, işlevi döndürür **EINVAL** ve ayarlar **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Mbsnbcat_s** işlevi ekler için *taşınmaya*, en fazla ilk *sayısı* bayt *src*. Bayt bu hemen null karakter önceyse *taşınmaya* ön bayt olup ilk bayt tarafından üzerine *src*. Aksi durumda, ilk baytını *src* sonlandırma null karakterinin üzerine yazar *taşınmaya*. İçinde bir null bayt görünürse *src* önce *sayısı* bayt eklenmiş, **_mbsnbcat_s** tüm baytlar ekler *src*, null kadar karakter. Varsa *sayısı* uzunluğundan daha büyük *src*, uzunluğu *src* yerine kullanılan *sayısı*. Sonuç dizesini bir null karakter tarafından sonlandırıldı. Kopyalama çakışma dizeleri arasında yer alıyorsa, tanımlanmamış bir davranıştır.

Çıkış değerini ayarı tarafından etkilenen **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Olanları yok dışında bu işlevler sürümleri özdeş sahip **_l** sonekini kullan geçerli yerel ayar ve sahip olanları **_l** soneki, bunun yerine yerel parametresini kullanın Bu geçirildi. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

C++'da, Bu işlevlerden birinin kullanımını şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer ve böylece boyutu bağımsız değişkeniyle belirtmek için gereksinimini ortadan kaldırır ve bunlar otomatik olarak yeni, daha güvenli işlevleriyle daha eski, daha az güvenli işlevlerini değiştirmek için kullanabilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

Bu işlevler hata ayıklama sürümleri ilk 0xFD arabellekle doldurun. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncat**|[strncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|**_mbsnbcat_s**|[wcsncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|
|**_tcsncat_s_l**|**_strncat_s_l**|**_mbsnbcat_s_l**|**_wcsncat_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbcat_s**|\<Mbstring.h >|
|**_mbsnbcat_s_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)<br/>
[_mbsnbcpy, _mbsnbcpy_l](mbsnbcpy-mbsnbcpy-l.md)<br/>
[_mbsnbcpy_s, _mbsnbcpy_s_l](mbsnbcpy-s-mbsnbcpy-s-l.md)<br/>
[_mbsnbset, _mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)<br/>
