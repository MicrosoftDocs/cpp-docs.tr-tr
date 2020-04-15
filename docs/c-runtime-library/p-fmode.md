---
title: __p__fmode
ms.date: 4/2/2020
api_name:
- __p__fmode
- _o___p__fmode
api_location:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__fmode
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
ms.openlocfilehash: aecba640099719f90db8bbd5dbe386ea99aae45d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349241"
---
# <a name="__p__fmode"></a>__p__fmode

Dosya G/Ç işlemleri için varsayılan `_fmode` *dosya çeviri modunu* belirten genel değişkene işaret eder.

## <a name="syntax"></a>Sözdizimi

```cpp
int* __p__fmode(
   );
```

## <a name="return-value"></a>Dönüş Değeri

Genel değişkene `_fmode` işaretçi.

## <a name="remarks"></a>Açıklamalar

İşlev `__p__fmode` yalnızca dahili kullanım içindir ve kullanıcı kodundan çağrılmamalıdır.

Dosya çeviri [modu,](../c-runtime-library/reference/open-wopen.md) `binary` _open `text` ve [_pipe](../c-runtime-library/reference/pipe.md) G/Ç işlemleri için çeviri veya Daha fazla bilgi için [_fmode.](../c-runtime-library/fmode.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__p\__fmode|stdlib.h|
