---
title: _strdate_s, _wstrdate_s
ms.date: 11/04/2016
api_name:
- _strdate_s
- _wstrdate_s
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
- api-ms-win-crt-time-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: fadd30ec81cff59d675212e59c8513656c7b2f35
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940744"
---
# <a name="_strdate_s-_wstrdate_s"></a>_strdate_s, _wstrdate_s

Geçerli sistem tarihini bir arabelleğe kopyalayın. Bu sürümler, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle birlikte [_wstrdate, _strdate](strdate-wstrdate.md) sürümleridir.

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

*arabelleğin*<br/>
Biçimlendirilen Tarih dizesiyle doldurulacak, arabellek işaretçisi.

*numberOfElements*<br/>
Arabelleğin boyutu.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Hata varsa dönüş değeri bir hata kodudur. Hata kodları ERRNO içinde tanımlanmıştır. Olsun Bu işlev tarafından oluşturulan tam hatalar için aşağıdaki tabloya bakın. Hata kodları hakkında daha fazla bilgi için bkz. [errno](../../c-runtime-library/errno-constants.md).

## <a name="error-conditions"></a>Hata koşulları

|*arabelleğin*|*numberOfElements*|döndürülmesini|*Arabelleğin* içeriği|
|--------------|------------------------|------------|--------------------------|
|**DEĞER**|kaydedilmemiş|**EINVAL**|değiştirilmedi|
|**Null** değil (geçerli arabelleğe işaret ediyor)|0|**EINVAL**|değiştirilmedi|
|**Null** değil (geçerli arabelleğe işaret ediyor)|0 < *numberOfElements* < 9|**EINVAL**|Boş dize|
|**Null** değil (geçerli arabelleğe işaret ediyor)|*numberOfElements* > = 9|0|Geçerli tarih, açıklamalar bölümünde belirtildiği gibi biçimlendirilir|

## <a name="security-issues"></a>Güvenlik Sorunları

*NumberOfElements* parametresi 9 ' dan büyükse, arabellek Için geçersiz **null** olmayan bir değer geçirmek erişim ihlaline neden olur.

*Arabelleğin* gerçek boyutundan daha büyük olan boyut değerlerinin geçirilmesi arabellek taşmasına neden olur.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, **_strdate** ve **_wstrdate**'in daha güvenli sürümlerini sağlar. **_Strdate_s** işlevi, geçerli sistem tarihini *arabelleğe*göre işaret eden arabelleğe/, aa**gg**/**yy**olarak, DD 'nin ayı belirten iki **basamak,** **gg** günü temsil eden iki basamakla ve **yy** yılın son iki hanesi olur. Örneğin, **12/05/99** dizesi 5 Aralık 1999 ' i temsil eder. Arabellek en az 9 karakter uzunluğunda olmalıdır.

**_wstrdate_s** , **_strdate_s**öğesinin geniş karakterli bir sürümüdür; **_wstrdate_s** bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir. Bu işlevler, aynı şekilde davranır.

*Buffer* **null** Işaretçisiyse veya *numberOfElements* 9 karakterden azsa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1 döndürür ve arabellek **null** Ise veya *numberOfElements* değeri 0 ' dan küçük ya da buna eşitse, **EINVAL** **olarak** **errno** **olarak ayarlanır veya**9 ' dan küçük.

' C++De, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır) ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mapping"></a>Genel metin rutin eşleme:

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate_s**|**_strdate_s**|**_strdate_s**|**_wstrdate_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strdate**|\<Time. h >|
|**_wstrdate**|\<Time. h > veya \<wchar. h >|
|**_strdate_s**|\<Time. h >|

## <a name="example"></a>Örnek

[Zaman](time-time32-time64.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
