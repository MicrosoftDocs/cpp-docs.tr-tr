---
title: __indword
ms.date: 09/02/2019
f1_keywords:
- __indword_cpp
- __indword
helpviewer_keywords:
- in instruction
- __indword intrinsic
ms.assetid: 1068d686-586e-4e36-b962-d1d7c3315260
ms.openlocfilehash: 790b65c8a565124df92b82b7ea17174788086a96
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222111"
---
# <a name="__indword"></a>__indword

**Microsoft 'a özgü**

`in` Yönergeleri kullanarak belirtilen bağlantı noktasından bir çift verinin bir Double sözcüğünü okur.

## <a name="syntax"></a>Sözdizimi

```C
unsigned long __indword(
   unsigned short Port
);
```

### <a name="parameters"></a>Parametreler

*Bağ*\
'ndaki Okunacak bağlantı noktası.

## <a name="return-value"></a>Dönüş değeri

Bağlantı noktasından okunan sözcük.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__indword`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
