---
description: 'Hakkında daha fazla bilgi edinin: _CrtGetDumpClient'
title: _CrtGetDumpClient
ms.date: 11/04/2016
api_name:
- _CrtGetDumpClient
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CrtGetDumpClient
- _CrtGetDumpClient
helpviewer_keywords:
- _CrtGetDumpClient function
- CrtGetDumpClient function
ms.assetid: 9051867f-341b-493b-b53d-45d2b454a3ad
ms.openlocfilehash: b4163e6f4f252eddd304f2704c3f5a9aa62b5371
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319758"
---
# <a name="_crtgetdumpclient"></a>_CrtGetDumpClient

**_CLIENT_BLOCK** türü bellek bloklarının dökümünü yapmak için geçerli uygulama tanımlı işlevi alır (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Syntax

```C
_CRT_DUMP_CLIENT _CrtGetDumpClient( void );
```

## <a name="return-value"></a>Dönüş Değeri

Geçerli döküm yordamını döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtGetDumpClient** Işlevi, C çalışma zamanı hata ayıklama belleği döküm işlemi için **_CLIENT_BLOCK** bellek bloklarına depolanan nesneleri dökme eden geçerli kanca işlevini alır.

Diğer kanca özellikli çalışma zamanı işlevlerini kullanma ve kendi istemci tanımlı kanca işlevlerinizi yazma hakkında daha fazla bilgi için bkz. [hata ayıklama kanca Işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtGetDumpClient**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtSetDumpClient](crtsetdumpclient.md)<br/>
