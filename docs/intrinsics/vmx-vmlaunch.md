---
title: __vmx_vmlaunch | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __vmx_vmlaunch
dev_langs: C++
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 019c295130de7edf14285da813bed79db5ee5404
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vmxvmlaunch"></a>__vmx_vmlaunch
**Microsoft özel**  
  
 Geçerli sanal makine denetim yapısı (Windows VMCS) kullanarak VMX kök olmayan işlemi durumu (VM girin) arama uygulamasında yerleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned char __vmx_vmlaunch(  
   void);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|Değer|Açıklama|  
|-----------|-------------|  
|0|İşlemi başarılı oldu.|  
|1.|İşlem başarısız oldu bulunan genişletilmiş durumundaki `VM-instruction error field` , geçerli Windows VMCS.|  
|2|İşlem durumu olmadan başarısız oldu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir uygulama kullanarak bir VM girin işlemi gerçekleştirebilir [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) veya [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevi. [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) işlevi, başlatma durumu yalnızca bir Windows VMCS ile kullanılabilir `Clear`ve [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevi, başlatma durumu yalnızca bir Windows VMCS ile kullanılabilir `Launched`. Sonuç olarak, kullanmak [__vmx_vmclear](../intrinsics/vmx-vmclear.md) Windows VMCS için başlatma durumunu ayarlamak için işlevi `Clear`ve ardından [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) ilk VM girin işleminizi ve işlevini[__vmx_vmresume](../intrinsics/vmx-vmresume.md) sonraki VM girin işlemleri için işlevi.  
  
 `__vmx_vmlaunch` İşlevi eşdeğerdir `VMLAUNCH` makine yönergesi. Bu işlev bir ana bilgisayarın sanal makine İzleyici etkileşiminin bir konuk işletim sistemi ve uygulamaları destekler. Daha fazla bilgi için belge, "Intel Sanallaştırma teknik belirtim IA-32 Intel mimarisi," için arama sırasında numara C97063-002, belge [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__vmx_vmlaunch`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmresume](../intrinsics/vmx-vmresume.md)   
 [__vmx_vmclear](../intrinsics/vmx-vmclear.md)