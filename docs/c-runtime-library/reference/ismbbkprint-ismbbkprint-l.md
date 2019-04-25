---
title: _ismbbkprint, _ismbbkprint_l
ms.date: 11/04/2016
apiname:
- _ismbbkprint
- _ismbbkprint_l
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
- _ismbbkprint_l
- ismbbkprint
- _ismbbkprint
- ismbbkprint_l
helpviewer_keywords:
- _ismbbkprint function
- ismbbkprint_l function
- ismbbkprint function
- _ismbbkprint_l function
ms.assetid: 8d1d3258-1e34-4365-81ed-97c95de25475
ms.openlocfilehash: 9d30abb0bcb587aeb15087ceb80d60d54ac1bebe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157532"
---
# <a name="ismbbkprint-ismbbkprintl"></a>_ismbbkprint, _ismbbkprint_l

Belirtilen bir çok baytlı karakterin bir noktalama işareti olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbbkprint(
   unsigned int c
);
int _ismbbkprint_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Test edilecek tamsayı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_ismbbkprint** sıfır olmayan bir değer döndürür tamsayı *c* değil bir ASCII olmayan metin veya ASCII olmayan noktalama işareti sembolü ya da 0 olur. Örneğin, yalnızca kod sayfası 932 içinde **_ismbbkprint** katakana alfasayısal veya katakana noktalama için testler (aralık: 0xA1 - 0xDF). **_ismbbkprint** yerel ayara bağımlı karakter ayarları için geçerli yerel ayarı kullanır. **_ismbbkprint_l** geçirilen yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbbkprint**|\<Mbctype.h >|
|**_ismbbkprint_l**|\<Mbctype.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
