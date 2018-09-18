---
title: __p__fmode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
apitype: DLLExport
f1_keywords:
- __p__fmode
dev_langs:
- C++
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6c4dcea9e3f35bf5fd8dbfbed9273562ac3db551
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056345"
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