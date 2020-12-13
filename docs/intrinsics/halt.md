---
description: 'Hakkında daha fazla bilgi edinin: __halt'
title: __halt
ms.date: 09/02/2019
f1_keywords:
- __halt
- __halt_cpp
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
ms.openlocfilehash: e38478b14b59c910e6d6ac12f9cb69fa369e3459
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336979"
---
# <a name="__halt"></a>__halt

**Microsoft'a Özgü**

Etkin bir kesme, maskelenemeyen kesme (NMI) veya sıfırlama gerçekleşene kadar mikroişlemciyi halden çıkarır.

## <a name="syntax"></a>Syntax

```C
void __halt( void );
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__halt`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

`__halt`İşlevi `HLT` makine yönergesine eşdeğerdir ve yalnızca çekirdek modunda kullanılabilir. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) sitesinde "Intel mimarisi yazılım geliştiricisi el kitabı, toplu 2: yönerge kümesi başvurusu" belgesinde arama yapın.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
