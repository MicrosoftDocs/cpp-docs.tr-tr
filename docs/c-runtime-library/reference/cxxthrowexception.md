---
title: _CxxThrowException | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd3ab2994359e99e490422fbb2f11cf28a05d6e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="cxxthrowexception"></a>_CxxThrowException

Özel durum kaydı oluşturur ve özel durum işleme başlayabilmesi için çalışma zamanı ortamı çağırır.

## <a name="syntax"></a>Sözdizimi

```C
extern "C" void __stdcall _CxxThrowException(
   void* pExceptionObject
   _ThrowInfo* pThrowInfo
);
```

### <a name="parameters"></a>Parametreler

*pExceptionObject* özel durum oluşturdu nesne.

*pThrowInfo* özel durumu işlemek için gereken bilgileri.

## <a name="remarks"></a>Açıklamalar

Bu yöntem derleyici özel durumları işlemek için kullandığı bir salt derleyici dosyasına dahil edilir. Doğrudan kodunuzdan yöntemi çağırmanız gerekmez.

## <a name="requirements"></a>Gereksinimler

**Kaynak:** Throw.cpp

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
