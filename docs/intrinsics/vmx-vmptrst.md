---
description: 'Hakkında daha fazla bilgi edinin: __vmx_vmptrst'
title: __vmx_vmptrst
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmptrst
helpviewer_keywords:
- __vmx_vmptrst intrinsic
- VMPTRST instruction
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
ms.openlocfilehash: 216da453acf5c04e4189271185567841327571ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333523"
---
# <a name="__vmx_vmptrst"></a>__vmx_vmptrst

**Microsoft'a Özgü**

İşaretçiyi belirtilen adresteki geçerli sanal makine denetim yapısına (VMCS) depolar.

## <a name="syntax"></a>Sözdizimi

```C
void __vmx_vmptrst(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>Parametreler

*VmcsPhysicalAddress*\
'ndaki Geçerli VMCS işaretçisinin depolandığı adres.

## <a name="remarks"></a>Açıklamalar

VMCS işaretçisi 64 bitlik bir fiziksel adrestir.

`__vmx_vmptrst`İşlev, `VMPTRST` makine yönergesine eşdeğerdir. Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" belge numarası C97063-002 olan belgeyi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_vmptrst`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)
