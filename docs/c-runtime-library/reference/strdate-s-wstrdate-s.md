---
title: _strdate_s, _wstrdate_s
description: _strdate_s ve _wstrdate_s, geçerli tarihi bir arabelleğe yerleştirmeye yönelik _strdate ve _wstrdate işlevlerinin güvenli CRT sürümleridir.
ms.date: 11/01/2019
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
ms.openlocfilehash: 7d04c134fcd19753ac0cecf8cc3b87e902d92e83
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73625757"
---
# <a name="_strdate_s-_wstrdate_s"></a>_strdate_s, _wstrdate_s

Geçerli sistem tarihini bir arabelleğe kopyalayın. Bu işlevler, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [, _wstrdate ile _strdate](strdate-wstrdate.md) 'in sürümleridir.

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

*arabellek* \
Biçimlendirilen Tarih dizesini yerleştirmek için bir arabelleğin işaretçisi.

*boyut* \
Karakter birimlerindeki arabelleğin boyutu.

## <a name="return-value"></a>Dönüş değeri

Başarılıysa sıfır. Hata varsa dönüş değeri bir hata kodudur. Hata kodları ERRNO içinde tanımlanmıştır. Olsun Bu işlev tarafından oluşturulan tam hatalar için aşağıdaki tabloya bakın. Hata kodları hakkında daha fazla bilgi için bkz. [errno](../../c-runtime-library/errno-constants.md).

## <a name="error-conditions"></a>Hata koşulları

|*arabelleğin*|*boyutla*|döndürülmesini|*Arabelleğin* içeriği|
|--------------|------------------------|------------|--------------------------|
|**DEĞER**|kaydedilmemiş|**EıNVAL**|değiştirilmedi|
|**Null** değil (geçerli arabelleğe işaret ediyor)|0|**EıNVAL**|değiştirilmedi|
|**Null** değil (geçerli arabelleğe işaret ediyor)|0 < *boyutu* < 9|**EıNVAL**|Boş dize|
|**Null** değil (geçerli arabelleğe işaret ediyor)|*boyut* > = 9|0|Geçerli tarih, açıklamalar bölümünde belirtildiği gibi biçimlendirilir|

## <a name="security-issues"></a>Güvenlik sorunları

*Arabellek* için GEÇERSIZ ve null olmayan bir değer geçirmek, *Boyut* parametresi dokuz ' den büyükse erişim ihlaline neden olur.

*Bellek* boyutunun gerçek boyutundan *daha büyük bir* değer geçirilmesi arabellek taşmasına neden olur.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, **_strdate** ve **_wstrdate**'in daha güvenli sürümlerini sağlar. **_Strdate_s** işlevi, geçerli sistem tarihini *arabelleğin*gösterdiği arabelleğe kopyalar. `mm/dd/yy`biçimlendirilir, burada `mm` iki basamaklı bir aydır, `dd` iki rakamlı gün ve `yy` yılın son iki hanesi olur. Örneğin `12/05/99` dize, 5 Aralık 1999 ' i temsil eder. Arabellek en az dokuz karakter uzunluğunda olmalıdır.

**_wstrdate_s** , **_strdate_s**öğesinin geniş karakterli bir sürümüdür; **_wstrdate_s** bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir. Bu işlevler, aynı şekilde davranır.

*Arabellek* **null** işaretçisiyse veya *Boyut* dokuz karakterden daha azsa, geçersiz parametre işleyicisi çağrılır. [Parametre doğrulamada](../../c-runtime-library/parameter-validation.md)açıklanmaktadır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1 döndürür. Arabellek **null** ise veya *Boyut* 0 ' dan küçük veya eşitse **errno** , **EINVAL** olarak ayarlanır. Ya da, *Boyut* 9 ' dan küçükse **errno** ' u **ERANGE** olarak ayarlar.

' C++De, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir. Aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir, bu da bir *Boyut* bağımsız değişkeni belirtme gereksinimini ortadan kaldırır. Ayrıca, güvenli olmayan işlevleri otomatik olarak yeni, daha güvenli karşılıklarla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama Kitaplığı sürümleri ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_Crtsetdebugfillthreshold](crtsetdebugfillthreshold.md)kullanın.

### <a name="generic-text-routine-mapping"></a>Genel metin rutin eşleme:

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate_s**|**_strdate_s**|**_strdate_s**|**_wstrdate_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strdate**|\<zaman. h >|
|**_wstrdate**|\<Time. h > veya \<wchar. h >|
|**_strdate_s**|\<zaman. h >|

## <a name="example"></a>Örnek

[Zaman](time-time32-time64.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Zaman yönetimi](../../c-runtime-library/time-management.md)\
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)\
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)\
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)\
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)\
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)\
[zaman, _time32, _time64](time-time32-time64.md)\
[_tzset](tzset.md)
