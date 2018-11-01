---
title: _mbbtype, _mbbtype_l
ms.date: 11/04/2016
apiname:
- _mbbtype
- _mbbtype_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbbtype_l
- mbbtype
- mbbtype_l
- _mbbtype
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
ms.openlocfilehash: a6d17b99e4314c2ab836a16129ab8a0e6ac7720e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467177"
---
# <a name="mbbtype-mbbtypel"></a>_mbbtype, _mbbtype_l

Önceki bayt üzerinde temel bayt türünü döndürür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _mbbtype(
   unsigned char c,
   int type
);
int _mbbtype_l(
   unsigned char c,
   int type,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Test etmek için karakter.

*Türü*<br/>
Sınanacak bayt türü.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbbtype** bir dizedeki bayt türünü döndürür. Bu değeri tarafından belirtilen bağlama duyarlı bir karardır *türü*, Denetim test koşulunu sağlar. *tür* dizesinde önceki bayt türüdür. Mbctype.h içindeki bildirim sabitleri aşağıdaki tabloda tanımlanır.

|Değeri *türü*|**_mbbtype** sınar|Dönüş değeri|*c*|
|---------------------|--------------------------|------------------|---------|
|1 dışındaki herhangi bir değer|Geçerli bir tek baytlı veya ön bayt|**_MBC_SINGLE** (0)|Tek baytlı (0x20 - 0x7E, 0xA1 - 0xDF)|
|1 dışındaki herhangi bir değer|Geçerli bir tek baytlı veya ön bayt|**_MBC_LEAD** (1)|Çok baytlı karakterinin bayt sağlama (0x81 - 0x9F, 0xE0 - 0xFC)|
|1 dışındaki herhangi bir değer|Geçerli bir tek baytlı veya müşteri adayı bayt|**_MBC_ILLEGAL**<br /><br /> ( -1)|Geçersiz karakter (hiçbir değer dışında 0x20 - 0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC|
|1.|Geçerli bayt|**_MBC_TRAIL** (2)|Bayt çok baytlı karakterin sondaki (0x40 - 0x7E, 0x80 – 0xfc aralığında)|
|1.|Geçerli bayt|**_MBC_ILLEGAL**<br /><br /> ( -1)|Geçersiz karakter (hiçbir değer dışında 0x20 - 0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC|

## <a name="remarks"></a>Açıklamalar

**_Mbbtype** işlevi çok baytlı bir karakterin bir baytın türünü belirler. Varsa değerini *türü* 1 dışındaki herhangi bir değer **_mbbtype** testler için çok baytlı bir karakterin geçerli bir tek baytlı veya müşteri adayı bayt. Varsa değerini *türü* 1 ' dir **_mbbtype** testler için çok baytlı bir karakterin geçerli sondaki baytı.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md) daha fazla bilgi için. **_Mbbtype** sürümü bu işlevin, bu yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır **_mbbtype_l** sürümü, bu kullanmalarıdır bunun yerine iletilen yerel ayar parametresini aynıdır . Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Önceki sürümlerde **_mbbtype** taşıyordu **chkctype**. Yeni kod için kullanmak **_mbbtype** yerine.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_mbbtype**|\<Mbstring.h >|\<Mbctype.h > *|
|**_mbbtype_l**|\<Mbstring.h >|\<Mbctype.h > *|

\* Dönüş değerleri kullanılan bildirim sabitleri için tanımları.

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
