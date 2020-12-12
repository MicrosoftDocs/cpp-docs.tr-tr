---
description: 'Hakkında daha fazla bilgi edinin: _CIfmod'
title: _CIfmod
ms.date: 4/2/2020
api_name:
- _CIfmod
- _o__CIfmod
api_location:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CIfmod
- CIfmod
helpviewer_keywords:
- CIfmod intrinsic
- _CIfmod intrinsic
ms.assetid: 7c050653-7ec6-4810-b3a7-7a0057ea65ed
ms.openlocfilehash: db5ebb6178b468d9f131c374c8ef128a90664d17
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246987"
---
# <a name="_cifmod"></a>_CIfmod

Yığındaki en üstteki iki değerin kayan nokta kalanını hesaplar.

## <a name="syntax"></a>Syntax

```cpp
void __cdecl _CIfmod();
```

## <a name="remarks"></a>Açıklamalar

İşlevin bu sürümünde `fmod` derleyicinin anladığı özelleştirilmiş bir çağırma kuralı vardır. Kopyaların oluşturulmasını ve YAZMAÇ ayrılmasına yardımcı olmasını önlediği için yürütmeyi hızlandırır.

Elde edilen değer yığının en üstüne gönderilir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

## <a name="requirements"></a>Gereksinimler

**Platform:** x86

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[fmod, fmodf](../c-runtime-library/reference/fmod-fmodf.md)
