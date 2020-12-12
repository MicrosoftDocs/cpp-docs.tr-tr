---
description: 'Hakkında daha fazla bilgi edinin: __p__fmode'
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__fmode
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
ms.openlocfilehash: da7cae9c881ebe042aa5d6003b50c09c65ea02d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213526"
---
# <a name="__p__fmode"></a>__p__fmode

`_fmode`Dosya g/ç işlemleri için varsayılan *Dosya çevirisi modunu* belirten genel değişkene işaret eder.

## <a name="syntax"></a>Syntax

```cpp
int* __p__fmode(
   );
```

## <a name="return-value"></a>Dönüş Değeri

`_fmode`Genel değişkene yönelik işaretçi.

## <a name="remarks"></a>Açıklamalar

`__p__fmode`İşlevi yalnızca dahili kullanım içindir ve kullanıcı kodundan çağrılmamalıdır.

Dosya çevirisi modu `binary` `text` , [_open](../c-runtime-library/reference/open-wopen.md) ve g/ç işlemleri [_pipe](../c-runtime-library/reference/pipe.md) için ya da çevirisini belirtir. Daha fazla bilgi için bkz. [_fmode](../c-runtime-library/fmode.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__p \_ _fmode|Stdlib. h|
