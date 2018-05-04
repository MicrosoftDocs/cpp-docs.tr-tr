---
title: _strdate_s, _wstrdate_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _strdate_s
- _wstrdate_s
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _strdate_s
- wstrdate_s
- _wstrdate_s
- strdate_s
- _tstrdate_s
dev_langs:
- C++
helpviewer_keywords:
- dates, copying
- tstrdate_s function
- wstrdate_s function
- _tstrdate_s function
- strdate_s function
- copying dates
- _strdate_s function
- _wstrdate_s function
ms.assetid: d41d8ea9-e5ce-40d4-864e-1ac29b455991
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8e4e9ff3783fc7a89e7af42ebf283209c034c0d6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="strdates-wstrdates"></a>_strdate_s, _wstrdate_s

Geçerli sistem tarihi bir arabellek kopyalayın. Sürümleri bunlar [_strdate, _wstrdate](strdate-wstrdate.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _strdate_s(
   char *buffer,
   size_t numberOfElements
);
errno_t _wstrdate_s(
   wchar_t *buffer,
   size_t numberOfElements
);
template <size_t size>
errno_t _strdate_s(
   char (&buffer)[size]
); // C++ only
template <size_t size>
errno_t _wstrdate_s(
   wchar_t (&buffer)[size]
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Biçimlendirilmiş tarih dizesi bilgileriyle doldurulan bir arabellek için bir işaretçi.

*numberOfElements*<br/>
Arabellek boyutu.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Bir hata olduğunda dönüş değeri bir hata kodudur. Hata kodları ERRNO içinde tanımlanmıştır. H; Bu işlev tarafından oluşturulan tam hatalar için aşağıdaki tabloya bakın. Hata kodları hakkında daha fazla bilgi için bkz: [errno](../../c-runtime-library/errno-constants.md).

## <a name="error-conditions"></a>Hata koşulları

|*Arabellek*|*numberOfElements*|Döndür|İçeriği *arabellek*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(any)|**EINVAL**|değiştirilmedi|
|Değil **NULL** (geçerli arabelleğe işaret eden)|0|**EINVAL**|değiştirilmedi|
|Değil **NULL** (geçerli arabelleğe işaret eden)|0 < *numberOfElements* < 9|**EINVAL**|Boş dize|
|Değil **NULL** (geçerli arabelleğe işaret eden)|*numberOfElements* > = 9|0|Geçerli tarih biçimli açıklamalar belirtildiği gibi|

## <a name="security-issues"></a>Güvenlik sorunları

Geçersiz bir olmayan geçirme **NULL** arabellek bir erişim ihlali neden olur için bir değer *numberOfElements* parametredir 9 büyük.

Boyut için değerleri geçirme gerçek boyutundan büyük *arabellek* arabellek taşması neden olur.

## <a name="remarks"></a>Açıklamalar

Bu işlevler daha güvenli sürümlerini sağlamak **_strdate** ve **_wstrdate**. **_Strdate_s** işlevi gösterdiği arabellek geçerli sistem tarihi kopyalar *arabellek*biçimlendirilmiş **mm**/**GG** / **yy**, burada **mm** olan iki basamak ayını **GG** olan gününü temsil eden iki basamaklı ve **yy**  yılın son iki basamaktan oluşur. Örneğin, dize **05/12/99** 5 Aralık 1999 temsil eder. Arabellek en az 9 karakter uzunluğunda olmalıdır.

**_wstrdate_s** bir joker karakter sürümü **_strdate_s**; bağımsız değişkeni ve dönüş değeri **_wstrdate_s** joker karakter dizelerdir. Bu işlevler aynı şekilde aksi davranır.

Varsa *arabellek* olan bir **NULL** işaretçisi veya *numberOfElements* 9'dan az karakter, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve **errno** için **EINVAL** arabellek ise **NULL** veya *numberOfElements*küçük veya eşit 0 veya kümesi **errno** için **ERANGE** varsa *numberOfElements* değerinden 9'dur.

C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mapping"></a>Genel metin rutin eşleme:

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate_s**|**_strdate_s**|**_strdate_s**|**_wstrdate_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strdate**|\<time.h >|
|**_wstrdate**|\<time.h > veya \<wchar.h >|
|**_strdate_s**|\<time.h >|

## <a name="example"></a>Örnek

Örneğin bkz [zaman](time-time32-time64.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
