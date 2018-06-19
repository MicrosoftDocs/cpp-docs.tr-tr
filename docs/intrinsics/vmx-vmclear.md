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
ms.openlocfilehash: 8da1e3d2c5b1a2018df0e46f085fede9b923fff8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332416"
---
# <a name="vmxvmclear"></a>__vmx_vmclear
**Microsoft özel**  
  
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
|[in] `VmcsPhysicalAddress`|Bir işaretçi bir 64-bit bellek konumuna temizlemek için Windows VMCS fiziksel adresini içerir.|  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|Değer|Açıklama|  
|-----------|-------------|  
|0|İşlemi başarılı oldu.|  
|1.|İşlem başarısız oldu bulunan genişletilmiş durumundaki `VM-instruction error field` , geçerli Windows VMCS.|  
|2|İşlem durumu olmadan başarısız oldu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir uygulama kullanarak bir VM girin işlemi gerçekleştirebilir [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) veya [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevi. [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) işlevi, başlatma durumu yalnızca bir Windows VMCS ile kullanılabilir `Clear`ve [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevi, başlatma durumu yalnızca bir Windows VMCS ile kullanılabilir `Launched`. Sonuç olarak, kullanmak [__vmx_vmclear](../intrinsics/vmx-vmclear.md) Windows VMCS için başlatma durumunu ayarlamak için işlevi `Clear`. Kullanım [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) işlevi ilk VM girin işleminiz ve [__vmx_vmresume](../intrinsics/vmx-vmresume.md) sonraki VM girin işlemleri için işlevi.  
  
 `__vmx_vmclear` İşlevi eşdeğerdir `VMCLEAR` makine yönergesi. Bu işlev bir ana bilgisayarın sanal makine İzleyici etkileşiminin bir konuk işletim sistemi ve uygulamaları destekler. Daha fazla bilgi için belge, "Intel Sanallaştırma teknik belirtim IA-32 Intel mimarisi," için arama sırasında numara C97063-002, belge [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__vmx_vmclear`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [__vmx_vmresume](../intrinsics/vmx-vmresume.md)