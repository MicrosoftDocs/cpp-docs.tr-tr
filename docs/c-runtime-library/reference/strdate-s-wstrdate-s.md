---
title: _strdate_s, _wstrdate_s
description: _strdate_s ve _wstrdate_s, geçerli tarihi bir arabelleğe koyan _strdate ve _wstrdate işlevlerinin güvenli CRT sürümleridir.
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: b4d977ba3546eae17218c63b1786fd26c784d340
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359830"
---
# <a name="_strdate_s-_wstrdate_s"></a>_strdate_s, _wstrdate_s

Geçerli sistem tarihini bir arabelleğe kopyalayın. Bu [işlevler, CRT'deki](strdate-wstrdate.md) Güvenlik Özellikleri'nde açıklandığı gibi güvenlik geliştirmeleriyle _wstrdate _strdate [sürümleridir.](../../c-runtime-library/security-features-in-the-crt.md)

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

*Arabellek*\
Biçimlendirilmiş tarih dizesini koymak için arabellek işaretçisi.

*Boyutu*\
Karakter birimlerindeki arabelleğe boyutu.

## <a name="return-value"></a>Döndürülen değer

Başarılı olursa sıfır. İade değeri, bir hata varsa bir hata kodudur. Hata kodları ERRNO'da tanımlanır. H; bu işlev tarafından oluşturulan tam hatalar için aşağıdaki tabloya bakın. Hata kodları hakkında daha fazla bilgi için [bkz.](../../c-runtime-library/errno-constants.md)

## <a name="error-conditions"></a>Hata koşulları

|*Arabellek*|*Boyutu*|Dönüş|*Arabellek* içeriği|
|--------------|------------------------|------------|--------------------------|
|**Null**|(herhangi bir)|**Eınval**|Değiştirilmedi|
|**NULL** değil (geçerli arabelleği işaret eden)|0|**Eınval**|Değiştirilmedi|
|**NULL** değil (geçerli arabelleği işaret eden)|0 < *boyutu* < 9|**Eınval**|Boş dize|
|**NULL** değil (geçerli arabelleği işaret eden)|*boyutu* >= 9|0|Açıklamalarta belirtildiği gibi biçimlendirilmiş geçerli tarih|

## <a name="security-issues"></a>Güvenlik sorunları

*Boyut* parametresi dokuzdan büyükse, *arabellek* için geçersiz, NULL olmayan bir değer geçişi bir erişim ihlaline neden olur.

Arabellek gerçek boyutundan daha büyük *buffer* *boyutu* için bir değer geçirerek bir arabellek taşma neden.

## <a name="remarks"></a>Açıklamalar

Bu işlevler **_strdate** ve **_wstrdate**daha güvenli sürümlerini sağlar. **_strdate_s** işlevi, geçerli sistem tarihini *arabellek*tarafından işaret edilen arabelleğe kopyalar. Biçimlendirilmiştir `mm/dd/yy`, iki `mm` basamaklı ay nerede, `dd` iki basamaklı gündür ve `yy` yılın son iki hanesidir. Örneğin, dize `12/05/99` 5 Aralık 1999 temsil eder. Arabellek en az dokuz karakter uzunluğunda olmalıdır.

**_wstrdate_s** **_strdate_s**geniş karakterli bir versiyonudur; bağımsız değişken ve **_wstrdate_s** döndürme değeri geniş karakterli dizeleri vardır. Bu işlevler aynı şekilde başka türlü çalışır.

*Arabellek* bir **NULL** işaretçisi olduğunda veya *boyut* dokuzkarakterden azsa, geçersiz parametre işleyicisi çağrılır. [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklanmıştır. Yürütmenin devam etmesine izin verilirse, bu işlevler -1 döndürüler. Arabellek **NULL** ise veya boyutu 0'a eşitse, **errno'yu** **EINVAL** olarak *ayarlarlar.* Veya, *boyutu* 9'dan küçükse **Errno'u** **ERANGE** olarak ayarlarlar.

C++'da, bu işlevlerin kullanımı şablon aşırı yükleri ile basitleştirilir. Aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkartabilir ve bu da *boyut* bağımsız değişkeni belirtme gereksinimini ortadan kaldırır. Ayrıca, güvenli olmayan işlevleri daha yeni ve daha güvenli muadilleriyle otomatik olarak değiştirebilirler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Bu işlevlerin hata ayıklama kitaplığı sürümleri önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mapping"></a>Genel metin rutin eşleme:

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate_s**|**_strdate_s**|**_strdate_s**|**_wstrdate_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strdate**|\<time.h>|
|**_wstrdate**|\<time.h> \<veya wchar.h>|
|**_strdate_s**|\<time.h>|

## <a name="example"></a>Örnek

[Zaman](time-time32-time64.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)\
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)\
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)\
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)\
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)\
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)\
[zaman, _time32, _time64](time-time32-time64.md)\
[_tzset](tzset.md)
