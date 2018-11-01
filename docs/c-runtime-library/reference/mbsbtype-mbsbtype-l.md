---
title: _mbsbtype, _mbsbtype_l
ms.date: 11/04/2016
apiname:
- _mbsbtype_l
- _mbsbtype
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
ms.openlocfilehash: 5c2927b4e4b68b1284341fe7e767ec50feb21a44
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566809"
---
# <a name="mbsbtype-mbsbtypel"></a>_mbsbtype, _mbsbtype_l

Bir dizedeki bayt türünü döndürür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Çok baytlı bir karakter dizisi adresi.

*Sayısı*<br/>
Baytı dize başından uzaklığı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbsbtype** ve **_mbsbtype_l** belirtilen bayttaki test sonucunu gösteren bir Integer değeri döndürür. Mbctype.h içindeki bildirim sabitleri aşağıdaki tabloda tanımlanır.

|Dönüş değeri|Byte türü|
|------------------|---------------|
|**_MBC_SINGLE** (0)|Tek baytlı karakter. Örneğin, kod sayfası 932'de, içinde **_mbsbtype** 0xDF belirtilen bayt 0x20-0x7E veya 0xA1 - aralığında ise 0 değerini döndürür.|
|**_MBC_LEAD** (1)|Çok baytlı karakterin ön baytı. Örneğin, kod sayfası 932'de, içinde **_mbsbtype** belirtilen bayt 0x81-0x9F veya 0xE0 - aralığında 0xfc aralığında ise, 1 döndürür.|
|**_MBC_TRAIL** (2)|Çok baytlı karakterin sondaki baytı. Örneğin, kod sayfası 932'de, içinde **_mbsbtype** belirtilen bayt 0x40-0x7E veya 0x80 – 0xFC aralığındaysa 2 döndürür.|
|**_MBC_ILLEGAL** (-1)|**NULL** dize, geçersiz karakter veya boş bayt uzaklığındaki baytı önce bulunan *sayısı* içinde *mbstr*.|

## <a name="remarks"></a>Açıklamalar

**_Mbsbtype** işlevi çok baytlı karakter dizesindeki bir baytın türünü belirler. İşlevi yalnızca uzaklığındaki baytı inceler *sayısı* içinde *mbstr*, belirlenen bayttan önceki geçersiz karakterleri yok sayılıyor.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevin sürümünü **_l** soneki, bu yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır sürümüyle **_l** soneki, onu kullanmalarıdır iletilmiş yerel ayar parametresini aynıdır Bunun yerine. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Giriş dizesi **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **_MBC_ILLEGAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_mbsbtype**|\<Mbstring.h >|\<Mbctype.h > *|
|**_mbsbtype_l**|\<Mbstring.h >|\<Mbctype.h > *|

\* Dönüş değerleri kullanılan bildirim sabitleri için.

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
