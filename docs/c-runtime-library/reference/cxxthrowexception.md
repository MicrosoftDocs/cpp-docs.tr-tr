---
description: 'Hakkında daha fazla bilgi edinin: _CxxThrowException'
title: _CxxThrowException
ms.date: 11/04/2016
api_name:
- _CxxThrowException
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
- CxxThrowException
- _CxxThrowException
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
ms.openlocfilehash: df4b1b30ba70ebf34bdb3cb4ae1c51a210f95a07
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327040"
---
# <a name="_cxxthrowexception"></a>_CxxThrowException

Özel durum kaydını oluşturur ve özel durumu işlemeye başlamak için çalışma zamanı ortamını çağırır.

## <a name="syntax"></a>Sözdizimi

```C
extern "C" void __stdcall _CxxThrowException(
   void* pExceptionObject
   _ThrowInfo* pThrowInfo
);
```

### <a name="parameters"></a>Parametreler

*pExceptionObject*<br/>
Özel durumu oluşturan nesne.

*pThrowInfo*<br/>
Özel durumu işlemek için gereken bilgiler.

## <a name="remarks"></a>Açıklamalar

Bu yöntem, derleyicinin özel durumları işlemek için kullandığı yalnızca derleyici dosyasına dahil edilmiştir. Yöntemi doğrudan kodunuzda çağırmayın.

## <a name="requirements"></a>Gereksinimler

**Kaynak:** Throw. cpp

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
