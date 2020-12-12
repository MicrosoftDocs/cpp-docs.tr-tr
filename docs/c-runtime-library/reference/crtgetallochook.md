---
description: 'Hakkında daha fazla bilgi edinin: _CrtGetAllocHook'
title: _CrtGetAllocHook
ms.date: 11/04/2016
api_name:
- _CrtGetAllocHook
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
- CrtGetAllocHook
- _CrtGetAllocHook
helpviewer_keywords:
- _CrtGetAllocHook function
- CrtGetAllocHook function
ms.assetid: 036acf7c-547a-4b3f-a636-80451070d7ed
ms.openlocfilehash: 997e3a03f0c9b56fda3a0fd89daf606a652136c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319771"
---
# <a name="_crtgetallochook"></a>_CrtGetAllocHook

C çalışma zamanı hata ayıklama belleği ayırma işlemine (yalnızca hata ayıklama sürümü) bağlama için istemci tanımlı geçerli ayırma işlevini alır.

## <a name="syntax"></a>Syntax

```C
_CRT_ALLOC_HOOK _CrtGetAllocHook( void );
```

## <a name="return-value"></a>Dönüş Değeri

Geçerli olarak tanımlanmış ayırma kanca işlevini döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtGetAllocHook** C çalışma zamanı hata ayıklama kitaplığı bellek ayırma işlemi için istemci tanımlı geçerli uygulama kanca işlevini alır.

Diğer kanca özellikli çalışma zamanı işlevlerini kullanma ve kendi istemci tanımlı kanca işlevlerinizi yazma hakkında daha fazla bilgi için bkz. [hata ayıklama kanca Işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtGetAllocHook**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetAllocHook](crtsetallochook.md)<br/>
