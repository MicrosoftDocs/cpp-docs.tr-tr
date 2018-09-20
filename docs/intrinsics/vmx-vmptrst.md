---
title: __vmx_vmptrst | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmptrst
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmptrst intrinsic
- VMPTRST instruction
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ccd691edb9ee799c8585fb33cb6b837e2871fc36
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413984"
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

#### <a name="parameters"></a>Parametreler

[in] *`VmcsPhysicalAddress` geçerli Windows VMCS işaretçinin depolandığı adresi.

## <a name="remarks"></a>Açıklamalar

Bir 64 bit fiziksel adresi Windows VMCS işaretçisidir.

`__vmx_vmptrst` İşlev, eşdeğer `VMPTRST` makine yönergesi. Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Daha fazla bilgi için "Intel Sanallaştırma teknik belirtimi IA-32 Intel mimari," Belge ara adresindeki sayı C97063 002 belge [Intel Corporation'da](https://software.intel.com/en-us/articles/intel-sdm) site.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__vmx_vmptrst`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)