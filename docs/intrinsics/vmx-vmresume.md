---
title: __vmx_vmresume | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmresume
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmresume intrinsic
- VMRESUME instruction
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9a2d898a6aad20788c0d77b42f3ca6107af5e9c
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678613"
---
# <a name="vmxvmresume"></a>__vmx_vmresume
**Microsoft'a özgü**  
  
 VMX kök olmayan işlemi, geçerli sanal makine denetim yapısı (Windows VMCS) kullanarak sürdürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned char __vmx_vmresume(  
   void);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|Değer|Açıklama|  
|-----------|-------------|  
|0|İşlem başarılı oldu.|  
|1.|İşlem başarısız oldu bulunan genişletilmiş durumundaki `VM-instruction error field` , geçerli Windows VMCS.|  
|2|İşlem durumu olmadan başarısız oldu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir uygulama kullanarak bir VM girin işlemi gerçekleştirebilir [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) veya `__vmx_vmresume` işlevi. `__vmx_vmlaunch` İşlevi, başlatma durumu yalnızca bir Windows VMCS ile kullanılabilir `Clear`ve `__vmx_vmresume` işlevi, başlatma durumu yalnızca bir Windows VMCS ile kullanılabilir `Launched`. Sonuç olarak, kullanmanız [__vmx_vmclear](../intrinsics/vmx-vmclear.md) işlevi için bir Windows VMCS başlatma durumunu ayarlamak için `Clear`ve ardından `__vmx_vmlaunch` ilk VM girin işlemi işlevi ve `__vmx_vmresume` sonraki VM girmek için işlevi işlemler.  
  
 `__vmx_vmresume` İşlev, eşdeğer `VMRESUME` makine yönergesi. Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. PDF belgesi, "Intel Sanallaştırma teknik belirtimi IA-32 Intel mimari," için arama hakkında daha fazla bilgi için numara C97063 002 belge [Intel Corporation'da](https://software.intel.com/en-us/articles/intel-sdm) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__vmx_vmresume`|X64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [__vmx_vmclear](../intrinsics/vmx-vmclear.md)