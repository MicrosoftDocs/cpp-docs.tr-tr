---
title: _ismbbalnum, _ismbbalnum_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _ismbbalnum
- _ismbbalnum_l
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
- _ismbbalnum
- ismbbalnum
- _ismbbalnum_l
- ismbbalnum_l
dev_langs:
- C++
helpviewer_keywords:
- _ismbbalnum_l function
- ismbbalnum function
- ismbbalnum_l function
- _ismbbalnum function
ms.assetid: 8025de50-a871-49fd-9ae6-f437b47aa987
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1d190fcc5175371a50f4613aaaf8f26747e17aa
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="ismbbalnum-ismbbalnuml"></a>_ismbbalnum, _ismbbalnum_l

Belirtilen birden çok baytlı karakter alfasayısal veya sayısal olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbbalnum(
   unsigned int c
);
int _ismbbalnum_l(
   unsigned int c
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Sınanacak tamsayı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_ismbbalnum** sıfır olmayan bir değer döndürür ifade:

`isalnum(c) || _ismbbkalnum(c)`

için sıfır olmayan bir değer olan *c*, veya değilse 0.

Bu işlev ile sürümü **_l** sonekidir aynı yerel ayara bağımlı davranışı için geçerli yerel yerine geçirilen yerel ayar kullanır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbbalnum**|\<Mbctype.h >|
|**_ismbbalnum_l**|\<Mbctype.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
