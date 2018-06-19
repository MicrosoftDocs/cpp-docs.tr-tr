---
title: _ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ismbcl2
- _ismbcl1
- _ismbcl0
- _ismbcl2_l
- _ismbcl1_l
- _ismbcl0_l
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29d80c6d26171d9ac347aae1ac488d1fcadb1fec
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403163"
---
# <a name="ismbcl0-ismbcl0l-ismbcl1-ismbcl1l-ismbcl2-ismbcl2l"></a>_ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l

**Kod sayfası 932 özel işlevler**, geçerli yerel veya belirtilen LC_CTYPE dönüştürme durumu kategorisinin kullanma.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*c*<br/>
Sınanacak karakter.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Karakter test durumu ya da 0 uymazsa mevcut değilse bu yordamlar her sıfır olmayan bir değer döndürür. Varsa *c* < = 255 ve karşılık gelen **_ismbb** yordamına (örneğin, **_ismbcalnum** karşılık gelen **_ismbbalnum**), Buna karşılık gelen dönüş değeri sonucudur **_ismbb** yordamı.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri belirli bir birden çok baytlı karakter verilen bir koşul için sınar.

Çıkış değerini ayarı tarafından etkilenen **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; sürümleriyle **_l** soneki, yerel ayar parametresi kullanmasını dışında aynıdır Bunun yerine geçirildi. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

|Yordam|(Yalnızca kod sayfası 932) koşulu test|
|-------------|-------------------------------------------|
|**_ismbcl0**|JIS olmayan Kanji: 0x8140 < =*c*< 0x889E =.|
|**_ismbcl0_l**|JIS olmayan Kanji: 0x8140 < =*c*< 0x889E =.|
|**_ismbcl1**|JIS düzey 1: 0x889F < =*c*< 0x9872 =.|
|**_ismbcl1_l**|JIS düzey 1: 0x889F < =*c*< 0x9872 =.|
|**_ismbcl2**|JIS düzey 2: 0x989F < =*c*< 0xEAA4 =.|
|**_ismbcl2_l**|JIS düzey 2: 0x989F < =*c*< 0xEAA4 =.|

İşlevler denetleyin belirtilen değere *c* test koşullar, yukarıda açıklanan ancak, denetleme eşleşmeleri *c* geçersiz bir birden çok baytlı karakter. Alt bayt aralıkları 0x00-0x3F, 0x7F veya 0xFD - 0xFF ise, bu işlevler karakter test koşulu karşılayan gösteren sıfır olmayan bir değer döndürür. Kullanım [_ismbbtrail](ismbbtrail-ismbbtrail-l.md) birden çok baytlı karakter tanımlı olup olmadığını sınamak için.

**Son kod sayfası 932 özel**

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbcl0**|\<Mbstring.h >|
|**_ismbcl0_l**|\<Mbstring.h >|
|**_ismbcl1**|\<Mbstring.h >|
|**_ismbcl1_l**|\<Mbstring.h >|
|**_ismbcl2**|\<Mbstring.h >|
|**_ismbcl2_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
