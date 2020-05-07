---
title: _free_locale
ms.date: 4/2/2020
api_name:
- _free_locale
- _o__free_locale
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __free_locale
- free_locale
- _free_locale
helpviewer_keywords:
- __free_locale function
- free_locale function
- locales, freeing
- _free_locale function
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
ms.openlocfilehash: 8dbc424c00464966605cce5c44118b88eb5335d3
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920431"
---
# <a name="_free_locale"></a>_free_locale

Bir yerel ayar nesnesini serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```C
void _free_locale(
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*locale*<br/>
Yerel ayar nesnesini ücretsiz olarak.

## <a name="remarks"></a>Açıklamalar

**_Free_locale** işlevi, **_get_current_locale** veya **_create_locale**çağrısından alınan yerel ayar nesnesini serbest bırakmak için kullanılır.

Bu işlevin önceki adı, **__free_locale** (iki önde gelen alt çizgi ile) kullanım dışıdır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|**Yordam**|Gerekli başlık|
|---------------|---------------------|
|**_free_locale**|\<locale. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_get_current_locale](get-current-locale.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
