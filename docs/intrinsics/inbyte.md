---
title: __inbyte
ms.date: 09/02/2019
f1_keywords:
- __inbyte
- __inbyte_cpp
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
ms.openlocfilehash: f0036763ed7315a54fbfe6dcc873b46b52f0730c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222145"
---
# <a name="__inbyte"></a>__inbyte

**Microsoft 'a özgü**

`in` Tarafından`Port`belirtilen bağlantı noktasından okunan tek bir bayt döndüren yönergeyi oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char __inbyte(
   unsigned short Port
);
```

### <a name="parameters"></a>Parametreler

*Bağ*\
'ndaki Okunacak bağlantı noktası.

## <a name="return-value"></a>Dönüş değeri

Belirtilen bağlantı noktasından okunan bayt.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__inbyte`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca iç öğe olarak kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
