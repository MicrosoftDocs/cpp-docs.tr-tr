---
title: __vmx_vmwrite | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __vmx_vmwrite
dev_langs: C++
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 00bc9fe617144db7de3425c5732b3f655b30c790
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite
**Microsoft özel**  
  
 Geçerli sanal makine denetim yapısı (Windows VMCS) belirtilen alan için belirtilen değer yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned char __vmx_vmwrite(   
   size_t Field,  
   size_t FieldValue  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`Field`|Yazılacak Windows VMCS alan.|  
|[in]`FieldValue`|Windows VMCS alana yazılacak değer.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 0  
 İşlemi başarılı oldu.  
  
 1.  
 İşlem başarısız oldu bulunan genişletilmiş durumundaki `VM-instruction error field` , geçerli Windows VMCS.  
  
 2  
 İşlem durumu olmadan başarısız oldu.  
  
## <a name="remarks"></a>Açıklamalar  
 `__vmx_vmwrite` İşlevi eşdeğerdir `VMWRITE` makine yönergesi. Değeri `Field` parametredir Intel belgelerinde açıklanan bir kodlanmış alan dizini. Daha fazla bilgi için belge, "Intel Sanallaştırma teknik belirtim IA-32 Intel mimarisi," için arama sırasında numara C97063-002, belge [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) site ve ardından o ek C bakın Belge.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__vmx_vmwrite`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmread](../intrinsics/vmx-vmread.md)