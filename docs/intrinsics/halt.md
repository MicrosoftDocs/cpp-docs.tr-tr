---
title: __halt
ms.date: 09/02/2019
f1_keywords:
- __halt
- __halt_cpp
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
ms.openlocfilehash: 66f5e05e7673523966ef35ac743fc585930b511c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222154"
---
# <a name="__halt"></a>__halt

**Microsoft 'a özgü**

Etkin bir kesme, maskelenemeyen kesme (NMI) veya sıfırlama gerçekleşene kadar mikroişlemciyi halden çıkarır.

## <a name="syntax"></a>Sözdizimi

```C
void __halt( void );
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__halt`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

`__halt` İşlevi `HLT` makine yönergesine eşdeğerdir ve yalnızca çekirdek modunda kullanılabilir. Daha fazla bilgi için belgeyi arayın, "Intel mimarisi yazılım geliştiricisi El Ile, birim 2: Yönerge kümesi başvurusu, " [Intel Corporation](https://software.intel.com/articles/intel-sdm) sitesinde.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
