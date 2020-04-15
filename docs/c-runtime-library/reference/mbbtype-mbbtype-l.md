---
title: _mbbtype, _mbbtype_l
ms.date: 4/2/2020
api_name:
- _mbbtype
- _mbbtype_l
- _o__mbbtype
- _o__mbbtype_l
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
ms.openlocfilehash: 7e2e818ed70ec393e4f81008f76ca9efe9cfa7e7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341405"
---
# <a name="_mbbtype-_mbbtype_l"></a>_mbbtype, _mbbtype_l

Önceki bayta göre bayt türünü döndürür.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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

*C*<br/>
Test etmek için karakter.

*Türü*<br/>
Test etmek için bayt türü.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbbtype** dizedeki bayt türünü döndürür. Bu karar, denetim testi koşulunu sağlayan *tür*değerine göre belirtildiği gibi, içeriğe duyarlıdır. *türü* dize önceki bayt türüdür. Aşağıdaki tablodaki manifesto sabitleri Mbctype.h'de tanımlanmıştır.

|*Türün* değeri|**_mbbtype** için testler|Döndürülen değer|*C*|
|---------------------|--------------------------|------------------|---------|
|1 hariç herhangi bir değer|Geçerli tek bayt veya kurşun bayt|**_MBC_SINGLE** (0)|Tek bayt (0x20 - 0x7E, 0xA1 - 0xDF)|
|1 hariç herhangi bir değer|Geçerli tek bayt veya kurşun bayt|**_MBC_LEAD** (1)|Çok bayt karakterli kurşun bayt (0x81 - 0x9F, 0xE0 - 0xFC)|
|1 hariç herhangi bir değer|Geçerli tek bayt veya kurşun bayt|**_MBC_ILLEGAL**<br /><br /> ( -1)|Geçersiz karakter (0x20 - 0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC hariç herhangi bir değer|
|1|Geçerli iz bayt|**_MBC_TRAIL** (2)|Çok bayt karakterli bayt (0x40 - 0x7E, 0x80 - 0xFC)|
|1|Geçerli iz bayt|**_MBC_ILLEGAL**<br /><br /> ( -1)|Geçersiz karakter (0x20 - 0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC hariç herhangi bir değer|

## <a name="remarks"></a>Açıklamalar

_mbbtype **_mbbtype** işlevi, çok bayt karakterdeki bayt türünü belirler. *Tür* değeri 1 dışında herhangi bir değerse, **_mbbtype** _mbbtype geçerli bir bayt veya çok bayt karakterli bir bayt için test olun. *Tür* değeri 1 **ise,** _mbbtype çok bayt karakterli geçerli bir iz baytını sınayın.

Çıktı değeri, yerel LC_CTYPE **kategori** ayarı ayarı etkilenir; daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md) bakın. Bu işlevin **_mbbtype** sürümü, bu yerele bağımlı davranış için geçerli yerel durumu kullanır; **_mbbtype_l** sürümü, bunun yerine geçirilen yerel parametreyi kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Önceki **sürümlerde, _mbbtype** **chkctype**seçildi. Yeni kod için bunun yerine **_mbbtype** kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_mbbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\*İade değerleri olarak kullanılan bildirim sabitlerinin tanımları için.

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
