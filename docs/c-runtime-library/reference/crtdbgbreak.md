---
title: _CrtDbgBreak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtDbgBreak
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
- _CrtDbgBreak
- CrtDbgBreak
dev_langs:
- C++
helpviewer_keywords:
- CrtDbgBreak function
- _CrtDbgBreak function
ms.assetid: 01f8b4a2-a2c7-4e1f-9f39-e573b4a7871f
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d63795ec929fe1333bfc0d55acc307b52d559faf
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="crtdbgbreak"></a>_CrtDbgBreak

Belirli bir kod satırında bir kesme noktası ayarlar. (Yalnızca hata ayıklama modunda kullanılır.)

## <a name="syntax"></a>Sözdizimi

```C
void _CrtDbgBreak( void );
```

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri yoktur.

## <a name="remarks"></a>Açıklamalar

**_CrtDbgBreak** işlevi ayarlar hata ayıklama kesme kodu belirli satırda işlevin yer. Bu işlev yalnızca hata ayıklama modunda kullanılır ve bağlı **_DEBUG** önceden tanımlanmış.

Kanca özellikli diğer çalışma zamanı işlevleri ve kendi istemci tarafından tanımlanan yazma hakkında daha fazla bilgi için kanca işlevleri, bkz: [yazma bilgisayarınızı kendi hata ayıklama kanca işlevleri](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtDbgBreak**|\<CRTDBG.h>|

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[__debugbreak](../../intrinsics/debugbreak.md)<br/>
