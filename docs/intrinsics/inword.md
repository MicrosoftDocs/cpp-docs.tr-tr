---
title: __inword
ms.date: 09/02/2019
f1_keywords:
- __inword_cpp
- __inword
helpviewer_keywords:
- in instruction
- __inword intrinsic
ms.assetid: 5c617edd-6709-40a1-aad2-40d5e39283c6
ms.openlocfilehash: 7daaf1abd5089716061f118e30e9534e5c5c18ee
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440971"
---
# <a name="__inword"></a>__inword

**Microsoft 'a özgü**

`in` yönergesini kullanarak belirtilen bağlantı noktasından verileri okur.

## <a name="syntax"></a>Sözdizimi

```C
unsigned short __inword(
   unsigned short Port
);
```

### <a name="parameters"></a>Parametreler

*Bağlantı noktası*\
'ndaki Okunacak bağlantı noktası.

## <a name="return-value"></a>Dönüş değeri

Okunan verilerin sözcüğü.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__inword`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
