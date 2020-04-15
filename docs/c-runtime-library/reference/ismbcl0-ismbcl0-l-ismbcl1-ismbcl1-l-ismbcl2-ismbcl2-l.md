---
title: _ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l
ms.date: 4/2/2020
api_name:
- _ismbcl2
- _ismbcl1
- _ismbcl0
- _ismbcl2_l
- _ismbcl1_l
- _ismbcl0_l
- _o__ismbcl0
- _o__ismbcl0_l
- _o__ismbcl1
- _o__ismbcl1_l
- _o__ismbcl2
- _o__ismbcl2_l
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
- ismbcl0
- _ismbcl1_l
- _ismbcl0
- ismbcl1
- ismbcl0_l
- _ismbcl2_l
- ismbcl2
- ismbcl1_l
- _ismbcl1
- _ismbcl0_l
- _ismbcl2
- ismbcl2_l
helpviewer_keywords:
- _ismbcl0_l function
- _ismbcl2 function
- _ismbcl1_l function
- ismbcl2 function
- _ismbcl1 function
- ismbcl0_l function
- ismbcl2_l function
- ismbcl1_l function
- ismbcl0 function
- ismbcl1 function
- _ismbcl2_l function
- _ismbcl0 function
ms.assetid: ee15ebd1-462c-4a43-95f3-6735836d626a
ms.openlocfilehash: 5d9481ecc8e574b602124103f8524e07270fe058
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343227"
---
# <a name="_ismbcl0-_ismbcl0_l-_ismbcl1-_ismbcl1_l-_ismbcl2-_ismbcl2_l"></a>_ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l

**Kod Sayfa 932 Geçerli**yerel alanı veya belirli bir LC_CTYPE dönüştürme durumu kategorisini kullanarak belirli işlevler.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbcl0(
   unsigned int c
);
int _ismbcl0_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcl1(
   unsigned int c
);
int _ismbcl1_l(
   unsigned int c ,
   _locale_t locale
);
int _ismbcl2(
   unsigned int c
);
int _ismbcl2_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Karakter test edilecek.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Karakter test koşulunu karşılarsa, bu yordamların her biri sıfır olmayan bir değer döndürür. *C* <= 255 ve karşılık gelen bir **_ismbb** yordamı varsa (örneğin, **_ismbcalnum** **_ismbbalnum**karşılık geliyorsa), sonuç ilgili **_ismbb** yordamının dönüş değeridir.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri belirli bir koşul için belirli bir çok bayt karakteri sınar.

Çıktı değeri, yerel LC_CTYPE **kategori** ayarı ayarı etkilenir; daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md) bakın. Bu işlevlerin **_l** soneki olmayan sürümleri, bu yerele bağımlı davranış için geçerli yerel durumu kullanır; **_l** soneki olan sürümler, bunun yerine geçirilen yerel parametreyi kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

|Yordam|Test koşulu (yalnızca kod sayfası 932)|
|-------------|-------------------------------------------|
|**_ismbcl0**|JIS olmayan Kanji: 0x8140<=*c*<=0x889E.|
|**_ismbcl0_l**|JIS olmayan Kanji: 0x8140<=*c*<=0x889E.|
|**_ismbcl1**|JIS seviye-1: 0x889F<=*c*<=0x9872.|
|**_ismbcl1_l**|JIS seviye-1: 0x889F<=*c*<=0x9872.|
|**_ismbcl2**|JIS düzey-2: 0x989F<=*c*<=0xEAA4.|
|**_ismbcl2_l**|JIS düzey-2: 0x989F<=*c*<=0xEAA4.|

İşlevler belirtilen değer *c'nin* yukarıda açıklanan test koşullarına uygun olup olmadığını denetler, ancak *c'nin* geçerli bir çok bayt karakter olup olmadığını denetlemez. Daha düşük bayt 0x00 - 0x3F, 0x7F veya 0xFF - 0xFF aralıklarında ysa, bu işlevler karakterin test durumunu karşıladığını belirten sıfır olmayan bir değer döndürer. Çok bayt karakterinin tanımlanıp tanımlanmadığını test etmek için [_ismbbtrail](ismbbtrail-ismbbtrail-l.md) kullanın.

**Bitiş Kodu Sayfa 932 Özel**

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbcl0**|\<mbstring.h>|
|**_ismbcl0_l**|\<mbstring.h>|
|**_ismbcl1**|\<mbstring.h>|
|**_ismbcl1_l**|\<mbstring.h>|
|**_ismbcl2**|\<mbstring.h>|
|**_ismbcl2_l**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Rutinleri](../../c-runtime-library/ismbc-routines.md)<br/>
[olduğunu, isw Rutinleri](../../c-runtime-library/is-isw-routines.md)<br/>
