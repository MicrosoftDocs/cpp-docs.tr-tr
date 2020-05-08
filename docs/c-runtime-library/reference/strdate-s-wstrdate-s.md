---
title: _strdate_s, _wstrdate_s
description: _strdate_s ve _wstrdate_s, _strdate ve _wstrdate işlevlerin güvenli CRT sürümleridir ve geçerli tarihi bir arabelleğe koyar.
ms.date: 4/2/2020
api_name:
- _strdate_s
- _wstrdate_s
- _o__strdate_s
- _o__wstrdate_s
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 7fe8d682ab515d5a11e90f0c26e956725644806e
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916909"
---
# <a name="_strdate_s-_wstrdate_s"></a>_strdate_s, _wstrdate_s

Geçerli sistem tarihini bir arabelleğe kopyalayın. Bu işlevler, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [_wstrdate _strdate](strdate-wstrdate.md) sürümleridir.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _strdate_s(
   char *buffer,
   size_t size
);
errno_t _wstrdate_s(
   wchar_t *buffer,
   size_t size
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

*arabelleğin*\
Biçimlendirilen Tarih dizesini yerleştirmek için bir arabelleğin işaretçisi.

*boyutla*\
Karakter birimlerindeki arabelleğin boyutu.

## <a name="return-value"></a>Döndürülen değer

Başarılıysa sıfır. Hata varsa dönüş değeri bir hata kodudur. Hata kodları ERRNO içinde tanımlanmıştır. Olsun Bu işlev tarafından oluşturulan tam hatalar için aşağıdaki tabloya bakın. Hata kodları hakkında daha fazla bilgi için bkz. [errno](../../c-runtime-library/errno-constants.md).

## <a name="error-conditions"></a>Hata koşulları

|*arabelleğin*|*boyutla*|Döndürülmesini|*Arabelleğin* içeriği|
|--------------|------------------------|------------|--------------------------|
|**DEĞER**|kaydedilmemiş|**EıNVAL**|Değiştirilmedi|
|**Null** değil (geçerli arabelleğe işaret ediyor)|0|**EıNVAL**|Değiştirilmedi|
|**Null** değil (geçerli arabelleğe işaret ediyor)|0 < *boyutu* < 9|**EıNVAL**|Boş dize|
|**Null** değil (geçerli arabelleğe işaret ediyor)|*boyut* >= 9|0|Geçerli tarih, açıklamalar bölümünde belirtildiği gibi biçimlendirilir|

## <a name="security-issues"></a>Güvenlik sorunları

*Arabellek* için GEÇERSIZ ve null olmayan bir değer geçirmek, *Boyut* parametresi dokuz ' den büyükse erişim ihlaline neden olur.

*Bellek* boyutunun gerçek boyutundan *daha büyük bir* değer geçirilmesi arabellek taşmasına neden olur.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, **_strdate** ve **_wstrdate**daha güvenli sürümlerini sağlar. **_Strdate_s** işlevi, geçerli sistem tarihini *arabelleğin*gösterdiği arabelleğe kopyalar. Bu, iki `mm/dd/yy`basamaklı bir `mm` ay `dd` , iki basamaklı bir gün ve `yy` yılın son iki basamağının bulunduğu biçimlendirilir. Örneğin, dize `12/05/99` 5 Aralık 1999 ' i temsil eder. Arabellek en az dokuz karakter uzunluğunda olmalıdır.

**_wstrdate_s** , **_strdate_s**geniş karakterli bir sürümüdür; **_wstrdate_s** bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir. Bu işlevler, aynı şekilde davranır.

*Arabellek* **null** işaretçisiyse veya *Boyut* dokuz karakterden daha azsa, geçersiz parametre işleyicisi çağrılır. [Parametre doğrulamada](../../c-runtime-library/parameter-validation.md)açıklanmaktadır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1 döndürür. Arabellek **null** ise veya *Boyut* 0 ' dan küçük veya eşitse **errno** , **EINVAL** olarak ayarlanır. Ya da, *Boyut* 9 ' dan küçükse **errno** ' u **ERANGE** olarak ayarlar.

C++ ' da, bu işlevlerin kullanımı şablon aşırı yüklemeleri tarafından basitleştirilmiştir. Aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir, bu da bir *Boyut* bağımsız değişkeni belirtme gereksinimini ortadan kaldırır. Ayrıca, güvenli olmayan işlevleri otomatik olarak yeni, daha güvenli karşılıklarla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama Kitaplığı sürümleri ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mapping"></a>Genel metin rutin eşleme:

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate_s**|**_strdate_s**|**_strdate_s**|**_wstrdate_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strdate**|\<Time. h>|
|**_wstrdate**|\<Time. h> veya \<wchar. h>|
|**_strdate_s**|\<Time. h>|

## <a name="example"></a>Örnek

[Zaman](time-time32-time64.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Zaman yönetimi](../../c-runtime-library/time-management.md)\
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)\
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)\
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)\
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)\
[mktime, _mktime32 _mktime64](mktime-mktime32-mktime64.md)\
[zaman, _time32, _time64](time-time32-time64.md)\
[_tzset](tzset.md)
