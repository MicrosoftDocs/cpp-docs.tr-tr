---
title: __p__fmode
ms.date: 11/04/2016
api_name:
- __p__fmode
api_location:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__fmode
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
ms.openlocfilehash: 6f7676fc5c9958be3d0567e6bf22a11367094150
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939979"
---
# <a name="__p__fmode"></a>__p__fmode

Dosya g/ç işlemleri için varsayılan *Dosya çevirisi modunu* belirten geneldeğişkeneişareteder.`_fmode`

## <a name="syntax"></a>Sözdizimi

```cpp
int* __p__fmode(
   );
```

## <a name="return-value"></a>Dönüş Değeri

`_fmode` Genel değişkene yönelik işaretçi.

## <a name="remarks"></a>Açıklamalar

`__p__fmode` İşlevi yalnızca dahili kullanım içindir ve kullanıcı kodundan çağrılmamalıdır.

Dosya çevirisi modu, `binary` [_open](../c-runtime-library/reference/open-wopen.md) ve [_pipe](../c-runtime-library/reference/pipe.md) g/ç işlemleri için ya da `text` çevirisini belirtir. Daha fazla bilgi için bkz. [_fmode](../c-runtime-library/fmode.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__p\__fmode|Stdlib. h|