---
title: _get_current_locale | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _get_current_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_current_locale
- __get_current_locale
- _get_current_locale
dev_langs:
- C++
helpviewer_keywords:
- get_current_locale function
- _get_current_locale function
- locales, getting information on
- __get_current_locale function
ms.assetid: 572217f2-a37a-4105-a293-a250b4fabd99
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6f20e69ca3ace4214915cd22f00fe2c9e8c9ffd
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="getcurrentlocale"></a>_get_current_locale

Geçerli yerel temsil eden bir yerel ayar nesnesi alır.

## <a name="syntax"></a>Sözdizimi

```C
_locale_t _get_current_locale(void);
```

## <a name="return-value"></a>Dönüş Değeri

Geçerli yerel temsil eden bir yerel ayar nesnesi.

## <a name="remarks"></a>Açıklamalar

**_Get_current_locale** işlevi alır ayarlanmış iş parçacığı yerel ayarı ve bu yerel ayara temsil eden bir yerel ayar nesnesi döndürür.

Bu işlev, önceki adını **__get_current_locale** (iki başında alt çizgi ile) kullanım dışı bırakıldı.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_current_locale**|\<Locale.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
