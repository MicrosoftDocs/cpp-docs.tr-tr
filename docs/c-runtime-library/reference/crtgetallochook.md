---
title: _CrtGetAllocHook | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtGetAllocHook
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
apitype: DLLExport
f1_keywords:
- CrtGetAllocHook
- _CrtGetAllocHook
dev_langs:
- C++
helpviewer_keywords:
- _CrtGetAllocHook function
- CrtGetAllocHook function
ms.assetid: 036acf7c-547a-4b3f-a636-80451070d7ed
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a0b1515e82d35159766993373f1dd6d8325f3b9
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="crtgetallochook"></a>_CrtGetAllocHook

C çalışma zamanı hata ayıklama bellek ayırma işlemine (yalnızca hata ayıklama sürümü) takma için geçerli istemci tarafından tanımlanan ayırma işlevi alır.

## <a name="syntax"></a>Sözdizimi

```C
_CRT_ALLOC_HOOK _CrtGetAllocHook( void );
```

## <a name="return-value"></a>Dönüş Değeri

Şu anda tanımlanmış ayırma kanca işlevi döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtGetAllocHook** C çalışma zamanı hata ayıklama kitaplığı bellek ayırma işlemi için geçerli istemci tarafından tanımlanan uygulama kanca işlevini alır.

Kanca özellikli diğer çalışma zamanı işlevleri ve kendi istemci tarafından tanımlanan yazma hakkında daha fazla bilgi için kanca işlevleri, bkz: [hata ayıklama kanca işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtGetAllocHook**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetAllocHook](crtsetallochook.md)<br/>
