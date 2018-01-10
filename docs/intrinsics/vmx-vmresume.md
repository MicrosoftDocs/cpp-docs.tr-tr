---
title: __vmx_vmresume | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __vmx_vmresume
dev_langs: C++
helpviewer_keywords:
- __vmx_vmresume intrinsic
- VMRESUME instruction
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ace3bfcc5063c705346543ad3d72e96e74dd6778
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="vmxvmresume"></a>__vmx_vmresume
**Microsoft özel**  
  
 VMX kök olmayan işlemi, geçerli sanal makine denetim yapısı (Windows VMCS) kullanarak devam eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned char __vmx_vmresume(  
   void);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|Değer|Açıklama|  
|-----------|-------------|  
|0|İşlemi başarılı oldu.|  
|1.|İşlem başarısız oldu bulunan genişletilmiş durumundaki `VM-instruction error field` , geçerli Windows VMCS.|  
|2|İşlem durumu olmadan başarısız oldu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir uygulama kullanarak bir VM girin işlemi gerçekleştirebilir [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) veya `__vmx_vmresume` işlevi. `__vmx_vmlaunch` İşlevi, başlatma durumu yalnızca bir Windows VMCS ile kullanılabilir `Clear`ve `__vmx_vmresume` işlevi, başlatma durumu yalnızca bir Windows VMCS ile kullanılabilir `Launched`. Sonuç olarak, kullanmak [__vmx_vmclear](../intrinsics/vmx-vmclear.md) Windows VMCS için başlatma durumunu ayarlamak için işlevi `Clear`ve ardından `__vmx_vmlaunch` işlevi ilk VM girin işleminiz ve `__vmx_vmresume` sonraki VM girmek için işlevi işlemler.  
  
 `__vmx_vmresume` İşlevi eşdeğerdir `VMRESUME` makine yönergesi. Bu işlev bir ana bilgisayarın sanal makine İzleyici etkileşiminin bir konuk işletim sistemi ve uygulamaları destekler. Daha fazla bilgi için PDF belgesi, "Intel Sanallaştırma teknik belirtim IA-32 Intel mimarisi," için arama sırasında numara C97063-002, belge [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__vmx_vmresume`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [__vmx_vmclear](../intrinsics/vmx-vmclear.md)