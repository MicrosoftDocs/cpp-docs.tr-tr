---
title: _mbsbtype, _mbsbtype_l
ms.date: 4/2/2020
api_name:
- _mbsbtype_l
- _mbsbtype
- _o__mbsbtype
- _o__mbsbtype_l
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
- mbsbtype
- mbsbtype_l
- _mbsbtype_l
- _mbsbtype
helpviewer_keywords:
- _mbsbtype function
- mbsbtype function
- _mbsbtype_l function
- mbsbtype_l function
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
ms.openlocfilehash: d71a061d9af5028c9bc6b4008f9904606a233592
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340870"
---
# <a name="_mbsbtype-_mbsbtype_l"></a>_mbsbtype, _mbsbtype_l

Dize içindeki bayt türünü döndürür.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int _mbsbtype(
   const unsigned char *mbstr,
   size_t count
);
int _mbsbtype_l(
   const unsigned char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*mbstr*<br/>
Çok bayt karakter dizisinin adresi.

*Sayısı*<br/>
Ipin başından bayt ofset.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

**_mbsbtype** ve **_mbsbtype_l** belirtilen bayt üzerinde test sonucunu gösteren bir tamsayı değeri döndürür. Aşağıdaki tablodaki manifesto sabitleri Mbctype.h'de tanımlanmıştır.

|Döndürülen değer|Bayt türü|
|------------------|---------------|
|**_MBC_SINGLE** (0)|Tek bayt karakter. Örneğin, kod sayfası 932'de, **_mbsbtype** belirtilen bayt 0x20 - 0x7E veya 0xA1 - 0xDF aralığındaysa _mbsbtype 0 döndürür.|
|**_MBC_LEAD** (1)|Çok bayt karakterli kurşun bayt. Örneğin, kod sayfası 932'de, belirtilen bayt 0x81 - 0x9F veya 0xE0 - 0xFC aralığındaysa **_mbsbtype** 1 döndürür.|
|**_MBC_TRAIL** (2)|Çok bayt karakterinin izsini takip ediyor. Örneğin, kod sayfası 932'de, belirtilen bayt 0x40 - 0x7E veya 0x80 - 0xFC aralığındaysa **_mbsbtype** 2 döndürür.|
|**_MBC_ILLEGAL** (-1)|**NULL** dize, geçersiz karakter veya null bayt önce bulunan byte ofset *sayısı* *ofset mbstr*.|

## <a name="remarks"></a>Açıklamalar

**_mbsbtype** işlevi, çok bayt karakter dizesinde bayt türünü belirler. İşlev, belirtilen bayt'ten önce geçersiz karakterleri yok *sayarak, mbstr'de*yalnızca ofset *sayısındaki* baytı inceler.

Çıktı değeri, yerel LC_CTYPE **kategori** ayarı ayarı etkilenir; daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md) bakın. Bu işlevin **_l** soneki olmayan sürümü, bu yerele bağımlı davranış için geçerli yerel durumu kullanır; **_l** soneki olan sürüm, bunun yerine geçirilen yerel parametreyi kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Giriş dizesi **NULL**ise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev **_MBC_ILLEGAL**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_mbsbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbsbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\*İade değerleri olarak kullanılan bildirim sabitleri için.

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
