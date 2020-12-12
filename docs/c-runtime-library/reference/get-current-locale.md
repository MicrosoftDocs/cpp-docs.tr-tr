---
description: 'Hakkında daha fazla bilgi edinin: _get_current_locale'
title: _get_current_locale
ms.date: 11/04/2016
api_name:
- _get_current_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_current_locale
- __get_current_locale
- _get_current_locale
helpviewer_keywords:
- get_current_locale function
- _get_current_locale function
- locales, getting information on
- __get_current_locale function
ms.assetid: 572217f2-a37a-4105-a293-a250b4fabd99
ms.openlocfilehash: 672914875aebbe020fbfab0c4958ce2963958432
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341496"
---
# <a name="_get_current_locale"></a>_get_current_locale

Geçerli yerel ayarı temsil eden yerel ayar nesnesini alır.

## <a name="syntax"></a>Syntax

```C
_locale_t _get_current_locale(void);
```

## <a name="return-value"></a>Dönüş Değeri

Geçerli yerel ayarı temsil eden yerel ayar nesnesi.

## <a name="remarks"></a>Açıklamalar

**_Get_current_locale** işlevi, iş parçacığı için ayarlanmış olan yerel ayarı alır ve bu yerel ayarı temsil eden bir yerel ayar nesnesi döndürür.

Bu işlevin önceki adı, **__get_current_locale** (iki önde gelen alt çizgi ile) kullanım dışıdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_current_locale**|\<locale.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
