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
ms.openlocfilehash: 666fdb8febebe133ae09ef3632cb38b6527d1210
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944493"
---
# <a name="_lock"></a>_lock

Çoklu iş parçacığı kilidi alır.

> [!IMPORTANT]
>  Bu işlev artık kullanılmıyor. Visual Studio 2015 ' den başlayarak CRT ' de kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
void __cdecl _lock
   int locknum
);
```

#### <a name="parameters"></a>Parametreler

*locknum*<br/>
'ndaki Elde edilecek kilit tanıtıcısı.

## <a name="remarks"></a>Açıklamalar

Kilit zaten alınırsa, bu yöntem kilidi yine de alır ve bir iç C çalışma zamanı (CRT) hatasına neden olur. Yöntem bir kilit elde edemez, önemli bir hatayla çıkar ve hata kodunu olarak `_RT_LOCK`ayarlar.

## <a name="requirements"></a>Gereksinimler

**Kaynak:** MLOCK. c

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_unlock](../c-runtime-library/unlock.md)
