---
title: __vmx_vmptrst
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmptrst
helpviewer_keywords:
- __vmx_vmptrst intrinsic
- VMPTRST instruction
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
ms.openlocfilehash: 4d7e2ed29daac276c9b6cba07a727371a212fd4a
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51331899"
---
# <a name="vmxvmptrst"></a>__vmx_vmptrst

**Microsoft'a özgü**

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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)