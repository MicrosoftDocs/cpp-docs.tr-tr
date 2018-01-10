---
title: __vmx_vmread | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __vmx_vmread
dev_langs: C++
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f4bc649f35eb2e3d3ce203529bf4010a3d4f53fe
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="vmxvmread"></a>__vmx_vmread
**Microsoft özel**  
  
 Belirtilen alan geçerli sanal makine denetim yapısından (Windows VMCS) okur ve belirtilen konuma yerleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned char __vmx_vmread(  
   size_t Field,  
   size_t *FieldValue  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`Field`|Okunacak Windows VMCS alan.|  
|[in]`FieldValue`|Bir işaretçi değeri depolamak için konum için okuma tarafından belirtilen Windows VMCS alanından `Field` parametresi.|  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|Değer|Açıklama|  
|-----------|-------------|  
|0|İşlemi başarılı oldu.|  
|1.|İşlem başarısız oldu bulunan genişletilmiş durumundaki `VM-instruction error field` , geçerli Windows VMCS.|  
|2|İşlem durumu olmadan başarısız oldu.|  
  
## <a name="remarks"></a>Açıklamalar  
 `__vmx_vmread` İşlevi eşdeğerdir `VMREAD` makine yönergesi. Değeri `Field` parametredir Intel belgelerinde açıklanan bir kodlanmış alan dizini. Daha fazla bilgi için belge, "Intel Sanallaştırma teknik belirtim IA-32 Intel mimarisi," için arama sırasında numara C97063-002, belge [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) site sonra ek C bu belgenin başvurun .  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__vmx_vmread`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)