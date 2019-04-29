---
title: __p__fmode
ms.date: 11/04/2016
apiname:
- __p__fmode
apilocation:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __p__fmode
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
ms.openlocfilehash: bdb390ef5ae7254c463a3abd66860559cebeeeb9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62342295"
---
# <a name="pfmode"></a>__p__fmode

İşaret `_fmode` varsayılan belirtir genel değişkeni *dosya çevirisi modu* dosya g/ç işlemleri için.

## <a name="syntax"></a>Sözdizimi

```cpp
int* __p__fmode(
   );
```

## <a name="return-value"></a>Dönüş Değeri

İşaretçi `_fmode` genel değişkeni.

## <a name="remarks"></a>Açıklamalar

`__p__fmode` İşlevi yalnızca dahili kullanım içindir ve kullanıcı kodundan çağrılmamalıdır.

Dosya çevirisi modu belirtir ya da `binary` veya `text` çeviri [_aç](../c-runtime-library/reference/open-wopen.md) ve [_pipe](../c-runtime-library/reference/pipe.md) g/ç işlemleri. Daha fazla bilgi için [_fmode](../c-runtime-library/fmode.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__p\__fmode|stdlıb.h|