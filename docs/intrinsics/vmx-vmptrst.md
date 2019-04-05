---
title: __vmx_vmptrst
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmptrst
helpviewer_keywords:
- __vmx_vmptrst intrinsic
- VMPTRST instruction
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
ms.openlocfilehash: 5ef02dd4401e0c10a84be008d7cb25841e0359cd
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029521"
---
# <a name="vmxvmptrst"></a>__vmx_vmptrst

**Microsoft'a Özgü**

Belirtilen adresteki geçerli sanal makine denetim yapısı (Windows VMCS) işaretçi depolar.

## <a name="syntax"></a>Sözdizimi

```
void __vmx_vmptrst(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>Parametreler

*VmcsPhysicalAddress*<br/>
[in] Geçerli Windows VMCS işaretçinin depolandığı adresi.

## <a name="remarks"></a>Açıklamalar

Bir 64 bit fiziksel adresi Windows VMCS işaretçisidir.

`__vmx_vmptrst` İşlev, eşdeğer `VMPTRST` makine yönergesi. Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Daha fazla bilgi için "Intel Sanallaştırma teknik belirtimi IA-32 Intel mimari," Belge ara adresindeki sayı C97063 002 belge [Intel Corporation'da](https://software.intel.com/articles/intel-sdm) site.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__vmx_vmptrst`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)