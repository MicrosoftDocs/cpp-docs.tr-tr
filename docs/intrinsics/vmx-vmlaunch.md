---
title: __vmx_vmlaunch | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmlaunch
dev_langs:
- C++
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9519250684ea4f354c2ccfbca5be64076d6376d6
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820587"
---
# <a name="vmxvmlaunch"></a>__vmx_vmlaunch

**Microsoft'a özgü**

Geçerli sanal makine denetim yapısı (Windows VMCS) kullanarak VMX kök olmayan işlem durumu (VM girin) arama uygulamada yerleştirir.

## <a name="syntax"></a>Sözdizimi

```
unsigned char __vmx_vmlaunch(
   void);
```

## <a name="return-value"></a>Dönüş Değeri

|Değer|Açıklama|
|-----------|-------------|
|0|İşlem başarılı oldu.|
|1.|İşlem başarısız oldu bulunan genişletilmiş durumundaki `VM-instruction error field` , geçerli Windows VMCS.|
|2|İşlem durumu olmadan başarısız oldu.|

## <a name="remarks"></a>Açıklamalar

Bir uygulama kullanarak bir VM girin işlemi gerçekleştirebilir [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) veya [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevi. [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) işlevi, başlatma durumu yalnızca bir Windows VMCS ile kullanılabilir `Clear`ve [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevi, başlatma durumu yalnızca bir Windows VMCS ile kullanılabilir `Launched`. Sonuç olarak, kullanmanız [__vmx_vmclear](../intrinsics/vmx-vmclear.md) işlevi için bir Windows VMCS başlatma durumunu ayarlamak için `Clear`ve ardından [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) işlevi ilk VM girin işleminizi ve [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevi için sonraki işlemleri VM girin.

`__vmx_vmlaunch` İşlev, eşdeğer `VMLAUNCH` makine yönergesi. Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Daha fazla bilgi için "Intel Sanallaştırma teknik belirtimi IA-32 Intel mimari," Belge ara adresindeki sayı C97063 002 belge [Intel Corporation'da](https://software.intel.com/articles/intel-sdm) site.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__vmx_vmlaunch`|X64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)<br/>
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)