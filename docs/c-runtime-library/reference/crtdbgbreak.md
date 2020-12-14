---
description: 'Hakkında daha fazla bilgi edinin: _CrtDbgBreak'
title: _CrtDbgBreak
ms.date: 11/04/2016
api_name:
- _CrtDbgBreak
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
- _CrtDbgBreak
- CrtDbgBreak
helpviewer_keywords:
- CrtDbgBreak function
- _CrtDbgBreak function
ms.assetid: 01f8b4a2-a2c7-4e1f-9f39-e573b4a7871f
ms.openlocfilehash: e92fa20e32ae02eab1b289878ad05826d8da0a85
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221572"
---
# <a name="_crtdbgbreak"></a>_CrtDbgBreak

Belirli bir kod satırında bir kesme noktası ayarlar. (Yalnızca hata ayıklama modunda kullanılır.)

## <a name="syntax"></a>Syntax

```C
void _CrtDbgBreak( void );
```

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri yok.

## <a name="remarks"></a>Açıklamalar

**_CrtDbgBreak** işlevi, işlevin bulunduğu belirli kod satırında bir hata ayıklama kesme noktası ayarlar. Bu işlev yalnızca hata ayıklama modunda kullanılır ve daha önce tanımlanan **_DEBUG** bağımlıdır.

Diğer kanca özellikli çalışma zamanı işlevlerini kullanma ve kendi istemci tanımlı kanca işlevlerinizi yazma hakkında daha fazla bilgi için, bkz. [kendi hata ayıklama kanca Işlevlerinizi yazma](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtDbgBreak**|\<CRTDBG.h>|

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[__debugbreak](../../intrinsics/debugbreak.md)<br/>
