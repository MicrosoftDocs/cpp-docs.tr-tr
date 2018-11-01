---
title: _CxxThrowException
ms.date: 11/04/2016
apiname:
- _CxxThrowException
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
- CxxThrowException
- _CxxThrowException
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
ms.openlocfilehash: 925b72a120b31029b76fa38bee73eea003511cd2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550339"
---
# <a name="cxxthrowexception"></a>_CxxThrowException

Özel durum kaydını oluşturur ve özel durum işlemeyi başlatmak için çalışma zamanı ortamı çağırır.

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
Özel durumu işlemek için gerekli bilgiler.

## <a name="remarks"></a>Açıklamalar

Bu yöntem, özel durumları işlemek için derleyicinin kullandığı yalnızca derleyici dosyasında da bulunmaktadır. Yöntemi doğrudan çağırmanız gerekmez.

## <a name="requirements"></a>Gereksinimler

**Kaynak:** Throw.cpp

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
