---
title: __pctype_func | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __pctype_func
apilocation:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- __pctype_func
dev_langs:
- C++
helpviewer_keywords:
- __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36c8dd0467dc50c9eba9db954f28711aa8525cd2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034299"
---
# <a name="pctypefunc"></a>__pctype_func

Karakter sınıflandırması bilgileri dizisi için bir işaretçi alır.

## <a name="syntax"></a>Sözdizimi

```cpp
const unsigned short *__pctype_func(
   )
```

## <a name="return-value"></a>Dönüş Değeri

Karakter sınıflandırması bilgileri dizisi için bir işaretçi.

## <a name="remarks"></a>Açıklamalar

Karakter sınıflandırması tabloda yer alan bilgiler yalnızca dahili kullanım içindir ve tür karakterleri sınıflandırmak çeşitli işlevler tarafından kullanılan `char`. Daha fazla bilgi için `Remarks` bölümünü [_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__pctype_func|CType.h|

## <a name="see-also"></a>Ayrıca Bkz.

[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)