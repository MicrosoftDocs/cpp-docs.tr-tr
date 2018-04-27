---
title: _ismbbtrail, _ismbbtrail_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _ismbbtrail
- _ismbbtrail_l
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
- _ismbbtrail
- ismbbtrail
- _ismbbtrail_l
- ismbbtrail_l
dev_langs:
- C++
helpviewer_keywords:
- ismbbtrail_l function
- _ismbbtrail function
- _ismbbtrail_l function
- ismbbtrail function
ms.assetid: dfdd0292-960b-4c1d-bf11-146e0fc80247
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b062dff3ef38743af21e2dcf75ea1cfb4a8c921
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="ismbbtrail-ismbbtraill"></a>_ismbbtrail, _ismbbtrail_l

Bir bayt birden çok baytlı karakter sonunda baytını olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbbtrail(
   unsigned int c
);
int _ismbbtrail_l(
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

**_ismbbtrail** sıfır olmayan bir değer döndürür tamsayı *c* birden çok baytlı karakter ikinci bayttır. Örneğin, kod sayfası 932 yalnızca, geçerli 0x40 için 0x7E ve 0x80 için 0xFC aralıktır.

## <a name="remarks"></a>Açıklamalar

**_ismbbtrail** geçerli yerel ayar için yerel ayara bağımlı davranışı kullanır. **_ismbbtrail_l** yerine geçirilen yerel kullandığı dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_ismbbtrail**|\<Mbctype.h > veya \<mbstring.h >|\<CType.h >, * \<lımıts.h >, \<stdlib.h >|
|**_ismbbtrail_l**|\<Mbctype.h > veya \<mbstring.h >|\<CType.h >, * \<lımıts.h >, \<stdlib.h >|

\* İçin test durumları için bildirim sabitleri.

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
