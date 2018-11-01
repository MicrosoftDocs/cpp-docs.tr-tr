---
title: __halt
ms.date: 11/04/2016
f1_keywords:
- __halt
- __halt_cpp
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
ms.openlocfilehash: d99a87b1f3fd70d1fffb724629e9acded025732a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617184"
---
# <a name="halt"></a>__halt

**Microsoft'a özgü**

Etkinleştirilmiş kesme, nonmaskable kesme (NMI) veya bir sıfırlama gerçekleşene kadar mikro durdurur.

## <a name="syntax"></a>Sözdizimi

```
void __halt( void );
```

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__halt`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

`__halt` İşlev, eşdeğer `HLT` makine yönerge ve yalnızca çekirdek modunda kullanılabilir. Belge için daha fazla bilgi için arama "Intel mimarisi yazılım geliştirici el ile 2 birim: yönerge kümesi başvurusu" konumunda [Intel Corporation'da](https://software.intel.com/articles/intel-sdm) site.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)