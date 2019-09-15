---
title: _mbbtype, _mbbtype_l
ms.date: 11/04/2016
api_name:
- _mbbtype
- _mbbtype_l
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
ms.openlocfilehash: ba4311921a0924d3f447feb1929a81ae1d816604
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952716"
---
# <a name="_mbbtype-_mbbtype_l"></a>_mbbtype, _mbbtype_l

Önceki bayta göre bayt türünü döndürür.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Sınanacak karakter.

*type*<br/>
Sınanacak bayt türü.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbbtype** bir dizedeki Byte türünü döndürür. Bu karar, denetim testi koşulunu sağlayan *tür*değeri tarafından belirtilen bağlama duyarlıdır. *tür* , dizedeki önceki baytın türüdür. Aşağıdaki tablodaki bildirim sabitleri Mbctype. h içinde tanımlanmıştır.

|*Tür* değeri|**_mbbtype** testleri|Dönüş değeri|*c*|
|---------------------|--------------------------|------------------|---------|
|1 dışında herhangi bir değer|Geçerli tek bayt veya ön bayt|**_MBC_SİNGLE** (0|Tek bayt (0x20-0x7E, 0xA1-0xDF)|
|1 dışında herhangi bir değer|Geçerli tek bayt veya ön bayt|**_MBC_LİDER** (1|Çok baytlı karakterin ön baytı (0x81-0x9F, 0xE0-0xFC)|
|1 dışında herhangi bir değer|Geçerli tek baytlı veya ön bayt|**_MBC_GEÇERSIZ**<br /><br /> ( -1)|Geçersiz karakter (0x20-0x7E, 0xA1-0xDF, 0x81-0x9F, 0xE0-0xFC dışında herhangi bir değer|
|1\.|Geçerli iz baytı|**_MBC_İZ** (|Çok baytlı karakterin sondaki baytı (0x40-0x7E, 0x80-0xFC)|
|1\.|Geçerli iz baytı|**_MBC_GEÇERSIZ**<br /><br /> ( -1)|Geçersiz karakter (0x20-0x7E, 0xA1-0xDF, 0x81-0x9F, 0xE0-0xFC dışında herhangi bir değer|

## <a name="remarks"></a>Açıklamalar

**_Mbbtype** işlevi, çok baytlı bir karakter içindeki bir baytın türünü belirler. *Tür* değeri, 1 dışında bir değer ise, çok baytlı bir karakterin geçerli tek baytlı veya ön bayt olması için, **_mbbtype** testi. Eğer *tür* değeri 1 ise, çok baytlı bir karakterin geçerli bir izleme baytı için **_mbbtype** testi yapın.

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md) . Bu işlevin **_mbbtype** sürümü, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_mbbtype_l** sürümü, yerine geçirilen yerel ayar parametresini kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Önceki sürümlerde, **_mbbtype** , **chkctype**olarak adlandırılmıştı. Yeni kod için bunun yerine **_mbbtype** kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_mbbtype**|\<mbstring. h >|\<Mbctype. h > *|
|**_mbbtype_l**|\<mbstring. h >|\<Mbctype. h > *|

\*Dönüş değeri olarak kullanılan bildirim sabitlerinin tanımları için.

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
