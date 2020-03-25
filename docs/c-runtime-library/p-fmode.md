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
ms.openlocfilehash: 2364a22d52c5bc418e4499a4a639c8e06559063a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171456"
---
# <a name="__p__fmode"></a>__p__fmode

Dosya g/ç işlemleri için varsayılan *Dosya çevirisi modunu* belirten `_fmode` genel değişkenine işaret eder.

## <a name="syntax"></a>Sözdizimi

```cpp
int* __p__fmode(
   );
```

## <a name="return-value"></a>Dönüş Değeri

`_fmode` genel değişkenine yönelik işaretçi.

## <a name="remarks"></a>Açıklamalar

`__p__fmode` işlevi yalnızca dahili kullanım içindir ve kullanıcı kodundan çağrılmamalıdır.

Dosya çevirisi modu [_open](../c-runtime-library/reference/open-wopen.md) ve [_Pipe](../c-runtime-library/reference/pipe.md) g/ç işlemleri için `binary` ya da `text` çevirisini belirtir. Daha fazla bilgi için bkz. [_fmode](../c-runtime-library/fmode.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__p\__fmode|Stdlib. h|
