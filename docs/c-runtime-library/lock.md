---
title: _lock
ms.date: 11/04/2016
api_name:
- _lock
api_location:
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcrt.dll
- msvcr120_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- lock
- _lock
helpviewer_keywords:
- lock function
- _lock function
ms.assetid: 29f77c37-30de-4b3d-91b6-030216e645a6
ms.openlocfilehash: 30cd84f008c7174d767ecf5e2b744a58b21e5000
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351090"
---
# <a name="_lock"></a>_lock

Çok iş parçacığı kilidi kazanır.

> [!IMPORTANT]
> Bu işlev geçersizdir. Visual Studio 2015'ten itibaren CRT'de kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
void __cdecl _lock
   int locknum
);
```

#### <a name="parameters"></a>Parametreler

*locknum*<br/>
[içinde] Elde etmek için kilidin tanımlayıcısı.

## <a name="remarks"></a>Açıklamalar

Kilit zaten elde edilmişse, bu yöntem kilidi yine de edinir ve dahili c çalışma süresi (CRT) hatasına neden olur. Yöntem bir kilit elde edemiyorsa, önemli bir hatayla çıkar `_RT_LOCK`ve hata kodunu .

## <a name="requirements"></a>Gereksinimler

**Kaynak:** mlock.c

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_unlock](../c-runtime-library/unlock.md)
