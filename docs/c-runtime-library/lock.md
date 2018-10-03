---
title: _Lock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _lock
apilocation:
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcrt.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords:
- lock
- _lock
dev_langs:
- C++
helpviewer_keywords:
- lock function
- _lock function
ms.assetid: 29f77c37-30de-4b3d-91b6-030216e645a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38cd49dd483b556c8bda95e7a77109a9d4682e7c
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48233625"
---
# <a name="lock"></a>_lock

Çoklu iş parçacığı kilidi alır.

> [!IMPORTANT]
>  Bu işlev artık kullanılmıyor. Visual Studio 2015'te başlayarak, CRT içinde kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
void __cdecl _lock
   int locknum
);
```

#### <a name="parameters"></a>Parametreler

*locknum*<br/>
[in] Kilit almaya tanımlayıcısı.

## <a name="remarks"></a>Açıklamalar

Kilidi zaten alınmış, bu yöntem kilit yine de alır ve bir iç C çalışma zamanı (CRT) hata neden olur. Yöntem bir kilit alınamıyor, önemli bir hata ile çıkar ve hata kodunu ayarlar `_RT_LOCK`.

## <a name="requirements"></a>Gereksinimler

**Kaynak:** mlock.c

## <a name="see-also"></a>Ayrıca Bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_unlock](../c-runtime-library/unlock.md)