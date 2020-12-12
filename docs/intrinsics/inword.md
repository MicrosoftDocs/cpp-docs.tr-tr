---
description: 'Hakkında daha fazla bilgi edinin: __inword'
title: __inword
ms.date: 09/02/2019
f1_keywords:
- __inword_cpp
- __inword
helpviewer_keywords:
- in instruction
- __inword intrinsic
ms.assetid: 5c617edd-6709-40a1-aad2-40d5e39283c6
ms.openlocfilehash: 8e2d698437cdb27a472872cfe24d7d0ab0a3c768
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167883"
---
# <a name="__inword"></a>__inword

**Microsoft'a Özgü**

Yönergeleri kullanarak belirtilen bağlantı noktasından verileri okur `in` .

## <a name="syntax"></a>Sözdizimi

```C
unsigned short __inword(
   unsigned short Port
);
```

### <a name="parameters"></a>Parametreler

*Bağ*\
'ndaki Okunacak bağlantı noktası.

## <a name="return-value"></a>Döndürülen değer

Okunan verilerin sözcüğü.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__inword`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
