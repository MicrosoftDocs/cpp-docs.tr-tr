---
title: _mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l
ms.date: 11/04/2016
api_name:
- _mbctohira
- _mbctohira_l
- _mbctokata
- _mbctokata_l
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbctokata
- mbctohira
- _mbctohira
- _mbctohira_l
- mbctokata
- mbctokata_l
- mbctohira_l
- _mbctokata_l
helpviewer_keywords:
- _mbctokata function
- _mbctokata_l function
- _mbctohira_l function
- mbctohira_l function
- mbctohira function
- mbctokata_l function
- _mbctohira function
- mbctokata function
ms.assetid: f949afd7-44d4-4f08-ac8f-1fef2c915a1c
ms.openlocfilehash: 6e158e933442256b1d712ba42afc28b94e2b123c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952551"
---
# <a name="_mbctohira-_mbctohira_l-_mbctokata-_mbctokata_l"></a>_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l

Hiragana ve katakana karakterleri arasında dönüştürür.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _mbctohira(
   unsigned int c
);
unsigned int _mbctohira_l(
   unsigned int c,
   _locale_t locale
);
unsigned int _mbctokata(
   unsigned int c
);
unsigned int _mbctokata_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Dönüştürülecek çok baytlı karakter.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, mümkünse, dönüştürülmüş karakter *c*'yi döndürür. Aksi takdirde, *c* karakterini değiştirilmemiş olarak döndürür.

## <a name="remarks"></a>Açıklamalar

**_Mbctohira** ve **_mbctoküta** işlevleri *c* karakterini test edin ve mümkünse aşağıdaki dönüşümlerden birini uygulayın.

|Çalıştırmasını|Dönüştürür|
|--------------|--------------|
|**_mbctohira**, **_mbctohik_l**|Çok baytlı Hiragana için çok baytlı Katakana.|
|**_mbctoküta**, **_mbctokata_l**|Çok baytlı Katakana için çok baytlı Hiragana.|

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md) . Bu işlevlerin sürümleri aynıdır, ancak **_l** sonekine sahip olmayan bu, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır ve bunun yerine **_l** sonekine sahip olanlar, geçirilen yerel ayar parametresini kullanır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Önceki sürümlerde, **_mbctohira** adlı **jtohira** ve **_mbctoküta** adı **jtoküta**olarak adlandırılmıştır. Yeni kod için yeni adları kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbctohira**|\<mbstring. h >|
|**_mbctohira_l**|\<mbstring. h >|
|**_mbctokata**|\<mbstring. h >|
|**_mbctokata_l**|\<mbstring. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)<br/>
[_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)<br/>
[_mbctombb, _mbctombb_l](mbctombb-mbctombb-l.md)<br/>
