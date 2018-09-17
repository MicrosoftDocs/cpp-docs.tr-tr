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
ms.openlocfilehash: fd5661a2b6aa257c91babcc3d17b1babb0b4d2c2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707167"
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
  
 `__vmx_vmclear` İşlev, eşdeğer `VMCLEAR` makine yönergesi. Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Daha fazla bilgi için "Intel Sanallaştırma teknik belirtimi IA-32 Intel mimari," Belge ara adresindeki sayı C97063 002 belge [Intel Corporation'da](https://software.intel.com/en-us/articles/intel-sdm) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__vmx_vmclear`|X64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [__vmx_vmresume](../intrinsics/vmx-vmresume.md)