---
title: _mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbctohira
- _mbctohira_l
- _mbctokata
- _mbctokata_l
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
- _mbctokata
- mbctohira
- _mbctohira
- _mbctohira_l
- mbctokata
- mbctokata_l
- mbctohira_l
- _mbctokata_l
dev_langs:
- C++
helpviewer_keywords:
- _mbctokata function
- _mbctokata_l function
- _mbctohira_l function
- mbctohira_l function
- mbctohira function
- mbctokata_l function
- _mbctohira function
- mbctokata function
ms.assetid: f949afd7-44d4-4f08-ac8f-1fef2c915a1c
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80f82098a033f7a3dec8cdb475476644381bed8d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="mbctohira-mbctohiral-mbctokata-mbctokatal"></a>_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l

Hiragana ve katakana karakterleri arasında dönüştürür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _mbctohira(
   unsigned int c
);
unsigned int _mbctohira_l(
   unsigned int c,
   _locale_t locale
);
unsigned int _mbctokata(
   unsigned int c
);
unsigned int _mbctokata_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Dönüştürmek için birden çok baytlı karakter.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri dönüştürülmüş karakteri döndürür *c*, mümkün olduğunda. Aksi takdirde karakteri döndürür *c* değişmez.

## <a name="remarks"></a>Açıklamalar

**_Mbctohira** ve **_mbctokata** işlevlerini test bir karakter *c* ve mümkünse, aşağıdaki dönüşümleri birini uygulayın.

|Yordamları|Dönüştürür|
|--------------|--------------|
|**_mbctohira**, **_mbctohira_l**|Birden çok baytlı hiragana katakana çok baytlı.|
|**_mbctokata**, **_mbctokata_l**|Çok baytlı hiragana birden çok baytlı katakana '.|

Çıkış değerini ayarı tarafından etkilenen **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Olanları yok dışında bu işlevler sürümleri özdeş sahip **_l** sonekini kullan geçerli yerel bu yerel ayara bağımlı davranış ve sahip olanları **_l** yerine soneki geçirilen yerel ayar parametresini kullanın. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Önceki sürümlerde, **_mbctohira** idi **jtohira** ve **_mbctokata** idi **jtokata**. İçin yeni kod, yeni adları kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbctohira**|\<Mbstring.h >|
|**_mbctohira_l**|\<Mbstring.h >|
|**_mbctokata**|\<Mbstring.h >|
|**_mbctokata_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)<br/>
[_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)<br/>
[_mbctombb, _mbctombb_l](mbctombb-mbctombb-l.md)<br/>
