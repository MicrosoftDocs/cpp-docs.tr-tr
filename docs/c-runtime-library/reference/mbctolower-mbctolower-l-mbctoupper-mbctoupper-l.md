---
description: 'Hakkında daha fazla bilgi edinin: _mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l'
title: _mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l
ms.date: 4/2/2020
api_name:
- _mbctolower_l
- _mbctoupper_l
- _mbctoupper
- _mbctolower
- _o__mbctolower
- _o__mbctolower_l
- _o__mbctoupper
- _o__mbctoupper_l
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
- mbctoupper_l
- mbctolower_l
- _mbctolower
- _mbctolower_l
- _mbctoupper
- mbctoupper
- mbctolower
- _mbctoupper_l
helpviewer_keywords:
- _mbctolower function
- mbctolower_l function
- totupper function
- _mbctoupper function
- totlower function
- _mbctoupper_l function
- mbctolower function
- _totupper function
- _mbctolower_l function
- mbctoupper_l function
- _totlower function
- mbctoupper function
ms.assetid: 787fab71-3224-4ed7-bc93-4dcd8023fc54
ms.openlocfilehash: abf09a7a96fc1df9f34f3263638c68da4f9991d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146451"
---
# <a name="_mbctolower-_mbctolower_l-_mbctoupper-_mbctoupper_l"></a>_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l

Çok baytlı bir karakterin durumunu sınar ve dönüştürür.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _mbctolower(
   unsigned int c
);
unsigned int _mbctolower_l(
   unsigned int c,
   _locale_t locale
);
unsigned int _mbctoupper(
   unsigned int c
);
unsigned int _mbctoupper_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*,*<br/>
Dönüştürülecek çok baytlı karakter.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, mümkünse, dönüştürülmüş karakter *c*'yi döndürür. Aksi takdirde, *c* karakterini değiştirilmemiş olarak döndürür.

## <a name="remarks"></a>Açıklamalar

İşlevler *c* karakterini test edin ve mümkünse aşağıdaki dönüşümlerden birini uygulayın.

|Çalıştırmasını|Dönüştürür|
|--------------|--------------|
|**_mbctolower**, **_mbctolower_l**|Büyük harfli karakter-küçük harf karakter.|
|**_mbctoupper**, **_mbctoupper_l**|Küçük harfli karakterden büyük harfe.|

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md) . Bu işlevin **_l** soneki olmadan sürümü, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip sürüm, bunun yerine geçirilen yerel ayar parametresini kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Önceki sürümlerde **_mbctolower** **jtolower** olarak adlandırılmıştı ve **_mbctoupper** **jtoupper** olarak adlandırılmıştı. Yeni kod için, bunun yerine yeni adları kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_totlower**|**ToLower**|**_mbctolower**|**kasadan düşük**|
|**_totlower_l**|**_tolower_l**|**_mbctolower_l**|**_towlower_t**|
|**_totupper**|**ToUpper**|**_mbctoupper**|**kasaüstü**|
|**_totupper_l**|**toupper_l**|**_mbctoupper_l**|**_towupper_l**|

## <a name="requirements"></a>Gereksinimler

|Çalıştırmasını|Gerekli başlık|
|--------------|---------------------|
|**_mbctolower**, **_mbctolower_l**|\<mbstring.h>|
|**_mbctoupper**, **_mbctoupper_l**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_mbbtombc, _mbbtombc_l](mbbtombc-mbbtombc-l.md)<br/>
[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)<br/>
[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)<br/>
[_mbctombb, _mbctombb_l](mbctombb-mbctombb-l.md)<br/>
