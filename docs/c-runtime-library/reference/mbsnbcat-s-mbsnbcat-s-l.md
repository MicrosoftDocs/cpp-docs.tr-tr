---
title: '`_mbsnbcat_s`, `_mbsnbcat_s_l`'
description: Microsoft Visual C++ `_mbsnbcat_s` ve işlevleri IÇIN API açıklaması `_mbsnbcat_s_l`
ms.date: 12/2/2020
api_name:
- _mbsnbcat_s_l
- _mbsnbcat_s
- _o__mbsnbcat_s
- _o__mbsnbcat_s_l
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
- _mbsnbcat_s
- mbsnbcat_s
- _mbsnbcat_s_l
- mbsnbcat_s_l
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
ms.openlocfilehash: c7198d806d8ebe077b423ff2135b5bdcf66ffac6
ms.sourcegitcommit: 9c45483572db4470fe5db5a7b596d5770303098c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2020
ms.locfileid: "96523120"
---
# <a name="_mbsnbcat_s-_mbsnbcat_s_l"></a>`_mbsnbcat_s`, `_mbsnbcat_s_l`

Çok baytlı bir karakter dizesine, en fazla bir çok baytlı karakter dizesinin ilk **n** baytını ekler. Bunlar [ `_mbsnbcat` , `_mbsnbcat_l` ](mbsnbcat-mbsnbcat-l.md) [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri olan sürümleridir.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*`dest`*\
Null ile sonlandırılmış çok baytlı karakter hedef dizesi.

*`sizeInBytes`*\
*`dest`* Arabelleğin bayt cinsinden boyutu.

*`src`*\
Null ile sonlandırılmış çok baytlı karakter kaynak dizesi.

*`count`*\
Eklenecek baytların sayısı *`src`* *`dest`* .

*`locale`*\
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi takdirde, bir hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|**`dest`**|*`sizeInBytes`*|*`src`*|Döndürülen değer|
|------------|-------------------|-----------|------------------|
|**`NULL`**|herhangi biri|herhangi biri|**`EINVAL`**|
|Herhangi bir|<= 0|herhangi biri|**`EINVAL`**|
|Herhangi bir|herhangi biri|**`NULL`**|**`EINVAL`**|

Hata koşullarından herhangi biri gerçekleşirse, işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklanan şekilde geçersiz bir parametre hatası oluşturur. Hata işlenirse, işlev döndürür **`EINVAL`** ve **errno** öğesini olarak ayarlar **`EINVAL`** .

## <a name="remarks"></a>Açıklamalar

**`_mbsnbcat_s`** İşlevi, *`dest`* en çok, ilk baytını öğesine ekler *`count`* *`src`* . İçindeki null karakterden hemen önce gelen bayt *`dest`* bir ön bayt ise, başlangıç baytı tarafından üzerine yazılır *`src`* . Aksi takdirde, ilk bayt, *`src`* öğesinin Sonlandırıcı null karakterinin üzerine yazar *`dest`* . Baytlardan önce içinde null bir bayt görünürse, *`src`* *`count`* **`_mbsnbcat_s`** tüm baytları *`src`* null karaktere kadar ekler. , *`count`* Uzunluğundan büyükse, yerine öğesinin *`src`* uzunluğu *`src`* kullanılır *`count`* . Elde edilen dize, null bir karakter tarafından sonlandırılır. Çakışan dizeler arasında kopyalama gerçekleşmesi durumunda davranış tanımsızdır.

Çıkış değeri **`LC_CTYPE`** yerel ayarın kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md) . Bu işlevlerin sürümleri aynıdır, ancak **`_l`** soneki olmayan geçerli yerel ayarı kullanır ve **`_l`** bunun yerine sonekine sahip olanlar, geçirilen yerel ayar parametresini kullanır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

C++ ' da, bu işlevlerin kullanımı şablon aşırı yüklemeleri tarafından basitleştirilmiştir. Aşırı Yüklemeler, bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldıran arabellek uzunluğunu otomatik olarak çıkarabilir ve daha eski, daha az güvenli işlevleri değiştirmek için daha yeni, daha güvenli işlevlerini otomatik olarak kullanabilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama Kitaplığı sürümleri ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için kullanın [`_CrtSetDebugFillThreshold`](crtsetdebugfillthreshold.md) .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|`Tchar.h` rutin|`_UNICODE` ve `_MBCS` tanımsız|`_MBCS` tanımlı|`_UNICODE` tanımlı|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**`_tcsncat_s`**|[strncat_s](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)|**`_mbsnbcat_s`**|[wcsncat_s](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)|
|**`_tcsncat_s_l`**|**`_strncat_s_l`**|**`_mbsnbcat_s_l`**|**`_wcsncat_s_l`**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**`_mbsnbcat_s`**|\<mbstring.h>|
|**`_mbsnbcat_s_l`**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenleme](../../c-runtime-library/string-manipulation-crt.md)\
[`_mbsnbcmp`, `_mbsnbcmp_l`](mbsnbcmp-mbsnbcmp-l.md)\
[`_strncnt`, `_wcsncnt`, `_mbsnbcnt`, `_mbsnbcnt_l`, `_mbsnccnt`, `_mbsnccnt_l`](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)\
[`_mbsnbcpy`, `_mbsnbcpy_l`](mbsnbcpy-mbsnbcpy-l.md)\
[`_mbsnbcpy_s`, `_mbsnbcpy_s_l`](mbsnbcpy-s-mbsnbcpy-s-l.md)\
[`_mbsnbset`, `_mbsnbset_l`](mbsnbset-mbsnbset-l.md)\
[`strncat`, `_strncat_l`, `wcsncat`, `_wcsncat_l`, `_mbsncat`, `_mbsncat_l`](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)\
[`strncat_s`, `_strncat_s_l`, `wcsncat_s`, `_wcsncat_s_l`, `_mbsncat_s`, `_mbsncat_s_l`](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)
