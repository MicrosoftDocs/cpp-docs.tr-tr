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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 813e6359d17f2ea4c6c0ded87a97c2afda243642
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919735"
---
# <a name="_ismbcl0-_ismbcl0_l-_ismbcl1-_ismbcl1_l-_ismbcl2-_ismbcl2_l"></a>_ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l

Geçerli yerel ayarı veya belirtilen LC_CTYPE dönüştürme durumu kategorisini kullanarak **kod sayfası 932 'e özgü işlevler**.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*,*<br/>
Sınanacak karakter.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri, karakter test koşulunu karşılıyorsa veya 0 değilse sıfır dışında bir değer döndürür. *C* <= 255 ise ve karşılık gelen bir **_ismbb** yordamı varsa (örneğin, **_ismbcalnum** **_ismbbalnum**karşılık gelir), sonuç karşılık gelen **_ismbb** yordamının dönüş değeridir.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, belirli bir koşul için verilen bir çok baytlı karakteri sınar.

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md) . **_L** soneki olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip sürümler, bunun yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

|Yordam|Test koşulu (yalnızca kod sayfası 932)|
|-------------|-------------------------------------------|
|**_ismbcl0**|JıS Kanji olmayan: 0x8140<=*c*<= 0x889E.|
|**_ismbcl0_l**|JıS Kanji olmayan: 0x8140<=*c*<= 0x889E.|
|**_ismbcl1**|JıS Level-1:0x889F<=*c*<= 0x9872.|
|**_ismbcl1_l**|JıS Level-1:0x889F<=*c*<= 0x9872.|
|**_ismbcl2**|JıS düzey-2:0x989F<=*c*<= 0xEAA4.|
|**_ismbcl2_l**|JıS düzey-2:0x989F<=*c*<= 0xEAA4.|

İşlevler, belirtilen *c* değerinin yukarıda açıklanan test koşulları ile eşleşip eşleşmediğini denetler, ancak *c* 'nin geçerli bir çok baytlı karakter olduğunu denetlemez. Alt bayt 0x00-0x3F, 0x7F veya 0xFD-0xFF aralıklarında bu işlevler, karakterin test koşulunu karşılayıp karşılamadığını belirten sıfır dışında bir değer döndürür. Çok baytlı karakterin tanımlanıp tanımlanmadığını test etmek için [_ismbbtrail](ismbbtrail-ismbbtrail-l.md) kullanın.

**Son kod sayfası 932 özgü**

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbcl0**|\<mbstring. h>|
|**_ismbcl0_l**|\<mbstring. h>|
|**_ismbcl1**|\<mbstring. h>|
|**_ismbcl1_l**|\<mbstring. h>|
|**_ismbcl2**|\<mbstring. h>|
|**_ismbcl2_l**|\<mbstring. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc yordamlar](../../c-runtime-library/ismbc-routines.md)<br/>
[, isw yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
