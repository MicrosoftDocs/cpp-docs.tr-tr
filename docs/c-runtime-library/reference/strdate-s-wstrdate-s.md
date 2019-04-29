---
title: _strdate_s, _wstrdate_s
ms.date: 11/04/2016
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
ms.openlocfilehash: 85c9ab7dcad68f3aa4832236461cd38b07d4ae44
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353995"
---
# <a name="strdates-wstrdates"></a>_strdate_s, _wstrdate_s

Geçerli sistem tarihini arabelleğe kopyalayın. Bunlar sürümleridir [_strdate, _wstrdate](strdate-wstrdate.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Biçimlendirilen tarih dizesi ile doldurulacak arabellek için işaretçi.

*numberOfElements*<br/>
Arabellek boyutu.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Bir hata varsa dönüş değeri bir hata kodudur. Hata kodları ERRNO içinde tanımlanır. H; Bu işlev tarafından oluşturulan tam hatalar için aşağıdaki tabloya bakın. Hata kodları hakkında daha fazla bilgi için bkz. [errno](../../c-runtime-library/errno-constants.md).

## <a name="error-conditions"></a>Hata koşulları

|*Arabellek*|*numberOfElements*|döndürülecek|İçeriğini *arabelleği*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(any)|**EINVAL**|değiştirilmedi|
|Değil **NULL** (geçerli arabelleğe işaret eden)|0|**EINVAL**|değiştirilmedi|
|Değil **NULL** (geçerli arabelleğe işaret eden)|0 < *numberOfElements* < 9|**EINVAL**|Boş dize|
|Değil **NULL** (geçerli arabelleğe işaret eden)|*numberOfElements* > = 9|0|Açıklamalar belirtildiği gibi biçimlendirilmiş geçerli tarih|

## <a name="security-issues"></a>Güvenlik Sorunları

Geçersiz bir olmayan geçirme **NULL** arabellek, erişim ihlali ile sonuçlanacak değer *numberOfElements* parametresi, 9'dan büyük.

Boyut değerleri geçirmeden gerçek boyutundan büyük *arabellek* arabellek taşmasına neden olur.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin daha güvenli sürümleri sağlamak **_strdate** ve **_wstrdate**. **_Strdate_s** işlevi tarafından işaret edilen arabellek için geçerli sistem tarihini kopyalar *arabellek*biçimlendirilmiş **mm**/**GG** / **yy**burada **mm** olan ayı temsil eden iki basamak **GG** olan iki basamak gününü ve **yy**  yılın son iki basamak. Örneğin, dize **12/05/99** 5 Aralık 1999 temsil eder. Arabelleğin en az 9 karakter uzunluğunda olmalıdır.

**_wstrdate_s** geniş karakterli sürümüdür **_strdate_s**; bağımsız değişkeni ve dönüş değeri **_wstrdate_s** geniş karakterli dizelerdir. Bu işlevler, aynı şekilde davranır.

Varsa *arabellek* olduğu bir **NULL** işaretçisi veya *numberOfElements* açıklandığı gibi geçersiz parametre işleyicisi çağrılır, 9'dan az karakter [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler -1 döndürür ve **errno** için **EINVAL** arabellek ise **NULL** veya *numberOfElements*eşit veya 0 ya da kümesi küçüktür **errno** için **ERANGE** varsa *numberOfElements* küçüktür 9'dur.

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kalkar) ve bunlar otomatik olarak eski ve güvenli olmayan işlevlerle daha yeni ve güvenli karşılıklarını değiştirir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mapping"></a>Genel metin yordam eşlemesi:

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate_s**|**_strdate_s**|**_strdate_s**|**_wstrdate_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strdate**|\<TIME.h >|
|**_wstrdate**|\<TIME.h > veya \<wchar.h >|
|**_strdate_s**|\<TIME.h >|

## <a name="example"></a>Örnek

Örneğin bakın [zaman](time-time32-time64.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
