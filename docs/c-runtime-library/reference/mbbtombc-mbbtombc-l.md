---
title: _mbbtombc, _mbbtombc_l
ms.date: 4/2/2020
api_name:
- _mbbtombc_l
- _mbbtombc
- _o__mbbtombc
- _o__mbbtombc_l
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
- _mbbtombc_l
- _mbbtombc
- mbbtombc_l
- mbbtombc
helpviewer_keywords:
- mbbtombc_l function
- mbbtombc function
- _mbbtombc_l function
- _mbbtombc function
ms.assetid: 78593389-b0fc-43b6-8c1f-2a6bf702d64e
ms.openlocfilehash: 5d26b06da1dcf8c53abda5d4ff2ee06ec3e7cd11
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341425"
---
# <a name="_mbbtombc-_mbbtombc_l"></a>_mbbtombc, _mbbtombc_l

Tek baytlık çok bayt karakterini karşılık gelen çift bayt lı çok bayt karaktere dönüştürür.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _mbbtombc(
   unsigned int c
);
unsigned int _mbbtombc_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Dönüştürmek için tek bayt karakter.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

**_mbbtombc** c'yi başarıyla *dönüştürürse,* çok baytlık bir karakter döndürür; aksi takdirde, *c*döndürür .

## <a name="remarks"></a>Açıklamalar

**_mbbtombc** işlevi, belirli bir tek bayt çok bayt karakterini karşılık gelen çift bayt lı çok bayt karaktere dönüştürür. Karakterler dönüştürülecek 0x20 - 0x7E veya 0xA1 - 0xDF aralığında olmalıdır.

Çıktı değeri, yerel LC_CTYPE **kategori** ayarı ayarı etkilenir; daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md) bakın. bu yerelliğe bağımlı davranış için geçerli yerel alanı **_mbbtombc** ve bunun yerine geçirilen yerel parametreyi **_mbbtombc_l** kullanması dışında, bu işlevin sürümleri aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Daha önceki **versiyonlarda, _mbbtombc** **hantozen**seçildi. Yeni kod için **_mbbtombc**kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbbtombc**|\<mbstring.h>|
|**_mbbtombc_l**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_mbctombb, _mbctombb_l](mbctombb-mbctombb-l.md)<br/>
