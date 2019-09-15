---
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
ms.openlocfilehash: 769621e92bf5f99f76f71b368a3b9a5cd0f79fd0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942418"
---
# <a name="_crtgetallochook"></a>_CrtGetAllocHook

C çalışma zamanı hata ayıklama belleği ayırma işlemine (yalnızca hata ayıklama sürümü) bağlama için istemci tanımlı geçerli ayırma işlevini alır.

## <a name="syntax"></a>Sözdizimi

```C
_CRT_ALLOC_HOOK _CrtGetAllocHook( void );
```

## <a name="return-value"></a>Dönüş Değeri

Geçerli olarak tanımlanmış ayırma kanca işlevini döndürür.

## <a name="remarks"></a>Açıklamalar

**_Crtgetallochook** , C çalışma zamanı hata ayıklama kitaplığı bellek ayırma işlemi için geçerli istemci tanımlı uygulama kanca işlevini alır.

Diğer kanca özellikli çalışma zamanı işlevlerini kullanma ve kendi istemci tanımlı kanca işlevlerinizi yazma hakkında daha fazla bilgi için bkz. [hata ayıklama kanca Işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtGetAllocHook**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetAllocHook](crtsetallochook.md)<br/>
