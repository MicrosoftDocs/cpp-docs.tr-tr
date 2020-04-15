---
title: _mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l
ms.date: 4/2/2020
api_name:
- _mbctohira
- _mbctohira_l
- _mbctokata
- _mbctokata_l
- _o__mbctohira
- _o__mbctohira_l
- _o__mbctokata
- _o__mbctokata_l
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 817f5598f6a7dddfd148b7d7023e260b7bddfa4b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341101"
---
# <a name="_mbctohira-_mbctohira_l-_mbctokata-_mbctokata_l"></a>_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l

Hiragana ve katakana karakterleri arasında dönüştürür.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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

*C*<br/>
Dönüştürmek için çok bayt karakter.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri dönüştürülen karakter *c*döndürür , mümkünse. Aksi takdirde *c* karakterini değiştirmeden döndürür.

## <a name="remarks"></a>Açıklamalar

**_mbctohira** ve **_mbctokata** işlevleri *c* karakterini test eder ve mümkünse aşağıdaki dönüşümlerden birini uygular.

|Rutin|Dönüştürür|
|--------------|--------------|
|**_mbctohira**, **_mbctohira_l**|Multibayt hiragana multibyte katakana.|
|**_mbctokata**, **_mbctokata_l**|Multibayt katakana multibayt hiragana.|

Çıktı değeri, yerel LC_CTYPE **kategori** ayarı ayarı etkilenir; daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md) bakın. Bu işlevlerin sürümleri aynıdır, ancak **_l** soneki olmayanlar bu yerelliğe bağımlı davranış için geçerli yerel alanı kullanır ve **_l** soneki olanlar bunun yerine geçirilen yerel parametreyi kullanır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Daha önceki versiyonlarda **_mbctohira** **jtohira,** **_mbctokata** ise **jtokata**olarak adlandırılmıştır. Yeni kod için yeni adları kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbctohira**|\<mbstring.h>|
|**_mbctohira_l**|\<mbstring.h>|
|**_mbctokata**|\<mbstring.h>|
|**_mbctokata_l**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)<br/>
[_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)<br/>
[_mbctombb, _mbctombb_l](mbctombb-mbctombb-l.md)<br/>
