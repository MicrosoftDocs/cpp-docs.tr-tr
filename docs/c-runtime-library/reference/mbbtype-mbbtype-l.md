---
title: _mbbtype, _mbbtype_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91b78b0dc57873810f96a793288da3f1457299de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404421"
---
# <a name="mbbtype-mbbtypel"></a>_mbbtype, _mbbtype_l

Önceki bayt üzerinde temel byte türü döndürür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Sınamak için bayt türü.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbbtype** bayt türü bir dize döndürür. Bu değeri tarafından belirtilen bağlama duyarlı bir karardır *türü*, Denetim test durumu sağlar. *tür* dizesindeki önceki bayt türüdür. Aşağıdaki tabloda bildirim sabitleri Mbctype.h içinde tanımlanmıştır.

|Değeri *türü*|**_mbbtype** sınar|Dönüş değeri|*c*|
|---------------------|--------------------------|------------------|---------|
|1 dışındaki herhangi bir değer|Geçerli bir tek bayt veya baytı|**_MBC_SINGLE** (0)|Tek bayt (0x20 - 0x7E, 0xA1 - 0xDF)|
|1 dışındaki herhangi bir değer|Geçerli bir tek bayt veya baytı|**_MBC_LEAD** (1)|Birden çok baytlı karakter baytını sağlama (0x81 - 0x9F, 0xE0 - 0xFC)|
|1 dışındaki herhangi bir değer|Geçerli bir tek baytlı veya sağlama bayt|**_MBC_ILLEGAL**<br /><br /> ( -1)|Geçersiz karakter (hiçbir değer 0x20 dışında-0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC|
|1.|Geçerli sondaki bayt|**_MBC_TRAIL** (2)|Birden çok baytlı karakter baytını sondaki (0x40 - 0x7E, 0x80 - 0xFC)|
|1.|Geçerli sondaki bayt|**_MBC_ILLEGAL**<br /><br /> ( -1)|Geçersiz karakter (hiçbir değer 0x20 dışında-0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC|

## <a name="remarks"></a>Açıklamalar

**_Mbbtype** fonksiyonu byte birden çok baytlı karakter türünü belirler. Varsa değerini *türü* 1 dışındaki herhangi bir değer **_mbbtype** testler için geçerli bir tek baytlı veya sağlama bayt birden çok baytlı karakter. Varsa değerini *türü* 1 ' dir **_mbbtype** testler için birden çok baytlı karakter geçerli sondaki bayt.

Çıkış değerini ayarı tarafından etkilenen **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md) daha fazla bilgi için. **_Mbbtype** bu işlev sürümünü kullanan geçerli yerel ayar için bu yerel ayara bağımlı davranışı; **_mbbtype_l** sürümüne sahip olduğunu aynı kullanmak dışında yerine geçirilen yerel ayar parametresi . Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Önceki sürümlerde, **_mbbtype** idi **chkctype**. Kullanmak için yeni kod, **_mbbtype** yerine.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_mbbtype**|\<Mbstring.h >|\<Mbctype.h > *|
|**_mbbtype_l**|\<Mbstring.h >|\<Mbctype.h > *|

\* Bildirim sabitleri tanımlarında, dönüş değeri olarak kullanılır.

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
