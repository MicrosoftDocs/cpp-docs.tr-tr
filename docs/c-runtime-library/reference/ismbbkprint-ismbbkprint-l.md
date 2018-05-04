---
title: _ismbbkprint, _ismbbkprint_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _ismbbkprint function
- ismbbkprint_l function
- ismbbkprint function
- _ismbbkprint_l function
ms.assetid: 8d1d3258-1e34-4365-81ed-97c95de25475
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1a6a215bac14f81d29d83a856313133fb4e88a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ismbbkprint-ismbbkprintl"></a>_ismbbkprint, _ismbbkprint_l

Belirli bir birden çok baytlı karakter noktalama işareti sembolü olup olmadığını belirler.

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
Sınanacak tamsayı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_ismbbkprint** sıfır olmayan bir değer döndürür tamsayı *c* değilse ASCII olmayan metni, ASCII olmayan noktalama işareti sembolü veya 0 değil. Örneğin, yalnızca kod sayfası 932 içinde **_ismbbkprint** katakana alfasayısal veya katakana noktalama için testler (aralık: 0xA1 - 0xDF). **_ismbbkprint** geçerli yerel ayar için yerel ayara bağımlı karakter ayarlarını kullanır. **_ismbbkprint_l** geçirilen yerel ayar kullandığı dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbbkprint**|\<Mbctype.h >|
|**_ismbbkprint_l**|\<Mbctype.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
