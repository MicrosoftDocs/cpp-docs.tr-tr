---
title: _get_current_locale
ms.date: 11/04/2016
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
helpviewer_keywords:
- get_current_locale function
- _get_current_locale function
- locales, getting information on
- __get_current_locale function
ms.assetid: 572217f2-a37a-4105-a293-a250b4fabd99
ms.openlocfilehash: 87c30ee701d8f7d3a89a0aa61ba18a7f854bc9b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511897"
---
# <a name="getcurrentlocale"></a>_get_current_locale

Geçerli yerel ayarı temsil eden bir yerel ayar nesnesini alır.

## <a name="syntax"></a>Sözdizimi

```C
_locale_t _get_current_locale(void);
```

## <a name="return-value"></a>Dönüş Değeri

Geçerli yerel ayarı temsil eden bir yerel ayar nesnesi.

## <a name="remarks"></a>Açıklamalar

**_Get_current_locale** işlevi şu anda ayarlanmış alır iş parçacığı için yerel ayar ve bu yerel ayar temsil eden bir yerel ayar nesnesi döndürür.

Bu işlev, önceki adını **__get_current_locale** (başında iki alt çizgi ile) kullanım dışı bırakıldı.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_current_locale**|\<Locale.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
