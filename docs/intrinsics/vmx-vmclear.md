---
title: __vmx_vmclear | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmclear
dev_langs:
- C++
helpviewer_keywords:
- VMCLEAR instruction
- __vmx_vmclear intrinsic
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13939e3e5407a7f78d199ef872ebddc3134b2a18
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820982"
---
# <a name="vmxvmclear"></a>__vmx_vmclear

**Microsoft'a özgü**

Belirtilen sanal makine denetim yapısı (Windows VMCS) başlatır ve başlatma durumuna ayarlar `Clear`.

## <a name="syntax"></a>Sözdizimi

```
unsigned char __vmx_vmclear(
   unsigned __int64 *VmcsPhysicalAddress
);
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*VmcsPhysicalAddress*|[in] Temizlenecek Windows VMCS fiziksel adresini içeren bir 64-bit bellek konumu için bir işaretçi.|

## <a name="return-value"></a>Dönüş Değeri

|Değer|Açıklama|
|-----------|-------------|
|0|İşlem başarılı oldu.|
|1.|İşlem başarısız oldu bulunan genişletilmiş durumundaki `VM-instruction error field` , geçerli Windows VMCS.|
|2|İşlem durumu olmadan başarısız oldu.|

## <a name="remarks"></a>Açıklamalar

Bir uygulama kullanarak bir VM girin işlemi gerçekleştirebilir [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) veya [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevi. [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) işlevi, başlatma durumu yalnızca bir Windows VMCS ile kullanılabilir `Clear`ve [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevi, başlatma durumu yalnızca bir Windows VMCS ile kullanılabilir `Launched`. Sonuç olarak, kullanmanız [__vmx_vmclear](../intrinsics/vmx-vmclear.md) işlevi için bir Windows VMCS başlatma durumunu ayarlamak için `Clear`. Kullanım [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) ilk VM girin işlemi için işlevi ve [__vmx_vmresume](../intrinsics/vmx-vmresume.md) VM girin sonraki işlemleri için işlevi.

`__vmx_vmclear` İşlev, eşdeğer `VMCLEAR` makine yönergesi. Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Daha fazla bilgi için "Intel Sanallaştırma teknik belirtimi IA-32 Intel mimari," Belge ara adresindeki sayı C97063 002 belge [Intel Corporation'da](https://software.intel.com/articles/intel-sdm) site.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__vmx_vmclear`|X64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)<br/>
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)